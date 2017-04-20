# [java] measure elapsed time


1. System.currentTimeMillis()
```
long startTime = System.currentTimeMillis();
// ...do something...
long estimatedTime = System.currentTimeMillis() - startTime;
```
2. _**System.nanoTime()**_
```
long startTime = System.nanoTime();    
// ...do something...    
long estimatedTime = System.nanoTime() - startTime;
```

ref : http://stackoverflow.com/questions/1770010/how-do-i-measure-time-elapsed-in-java