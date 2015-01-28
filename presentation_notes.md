## Capistrano presentation outline

1. What is capistrano
  * http://capistranorb.com/
  * "A remote server automation and deployment tool written in Ruby."
1. Word of warning
  * I'm only familiar with version 2 syntax, so for now thats what I will be covering
  * There are differences in syntax
1. Basics
  * Capistrano can be configured to do things across multiple machines, even in parallel
  * example: date
  
  Task: 
  ```
desc "Runs date on all_hosts"
task :date, :hosts => all_hosts do
  run "/bin/date"
end
  ```
  
  Example output
  ```
  bilsch@Euclid:data (master)$ cap date
  * 2015-01-27 19:52:21 executing `date'
  * executing multiple commands in parallel
    -> "else" :: "/bin/date"
    -> "else" :: "/bin/date"
    -> "else" :: "/bin/date"
    -> "else" :: "/bin/date"
    servers: ["bilsch.dyndns.org", "gir.home.bilsch.org", "udooq.home.bilsch.org", "pi.home.bilsch.org"]
    [gir.home.bilsch.org] executing command
    [udooq.home.bilsch.org] executing command
 ** [out :: udooq.home.bilsch.org] Tue Jan 27 19:52:21 EST 2015
*** [err :: gir.home.bilsch.org] stdin: is not a tty
 ** [out :: gir.home.bilsch.org] Tue Jan 27 19:52:21 EST 2015
    [pi.home.bilsch.org] executing command
 ** [out :: pi.home.bilsch.org] Tue Jan 27 19:52:21 EST 2015
    [bilsch.dyndns.org] executing command
 ** [out :: bilsch.dyndns.org] Tue Jan 27 19:52:22 EST 2015
    command finished in 1164ms
    bilsch@Euclid:data (master)$ echo $?
    0```
1. Wait, where I see the output? What if I want to use it for something?
   * Is httpd installed?
   
