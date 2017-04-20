# [Java] ThreadPool  by ExecutorService
### ExecutorService
```java
// SingleThread
ExecutorService single = Executors.newSingleThreadExecutor();
ExecutorService singleWithFactory = Executors.newSingleThreadExecutor(ThreadFactory);

// FixedThreadPool
ExecutorService fixed = Executors.newFixedThreadPool(FIXED_SIZE);
ExecutorService fixedWithFactory = Executors.newFixedThreadPool(FIXED_SIZE, ThreadFactory);

// CachedThreadPool
ExecutorService cached = Executors.newCachedThreadPool(); 
ExecutorService cachedWithFactory = Executors.newCachedThreadPool(ThreadFactory);

// WorkStealingPool, new feature in 1.8
ExecutorService workStealing = Executors.newWorkStealingPool();
ExecutorService workStealingParallelism = Executors.newWorkStealingPool(PARALLELISM);
```
### ScheduledExecutorService
```java
// SingleScheduledThread
ScheduledExecutorService singleScheduled = Executors.newSingleThreadScheduledExecutor();
ScheduledExecutorService singleScheduledWithFactory = Executors.newSingleThreadScheduledExecutor(ThreadFactory);

// ScheduledThreadPool
ScheduledExecutorService scheduled = Executors.newScheduledThreadPool(CORE_SIZE); 
ScheduledExecutorService scheduledWithFactory = Executors.newScheduledThreadPool(CORE_SIZE ThreadFactory);
```

### ThreadFactory interface
```java
public interface ThreadFactory {
	Thread newThread(Runnable r);
}
```adFactory {
	Thread newThread(Runnable r);
}
```