## Command Line

### Links
#### Command Line Video Series (Free)
| Name          | Link                                                            |
|---------------|-----------------------------------------------------------------|
| Wes Bos - Command Line Power User | https://www.youtube.com/playlist?list=PLu8EoSxDXHP7tXPJp5ZmUpuT7sFvrswzf |
| cmdchallenge - Command Line Interactive Quiz | https://cmdchallenge.com/ |

<br>

##### [Show all processes that are listening for traffic](https://en.wikipedia.org/wiki/Lsof)
```js
lsof -i -P -n | grep LISTEN
```

<br>

##### [Find out which processes are listening on a specified port](https://www.tecmint.com/find-out-which-process-listening-on-a-particular-port/)
```js
lsof -i :{pid}
```

<br>

##### [Get detailed information on a process](https://unix.stackexchange.com/a/106848/216496)
```js
ps aux | grep {pid}
```

<br>

##### [Kill a specified process](https://www.tecmint.com/how-to-kill-a-process-in-linux/)
```js
kill {pid}
```

<br>


