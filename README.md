# psscalabigpic



## 10. Cuncurrency
### 3 Future and ExecutionContext
```
import scala.concurrent.Future
var fut = fFuture{Thread.sleep(10000);1+1}
import scala.concurrent.ExecutionContext.Implicit.global
fut.isCompleted
fut.value
```


```
fut.onComplete({
  case Success(result)=>println(result)
  case Failure(e)=>println(e)
})
```

### 4 Futures Transformation
```
val salary = Future{Thread.sleep(20000);1}
val Bonus = = salary.map(value=>value+500)
```

### 5 Filtering and Collecting Futures
```
val salary = Future{ Thread.sleep(5000);1}
val salary = salary.collect{case salary if salary<50000=>salary+1}
```

### 6 Other Ways to Model Asynchronous Operation
##### success and failed
```
Future.successful("s")
Future.failed(new Exception())
```

##### promise
```
import scala.concurrent.{Future,Promise}
val promise = Promise[Int]
promise.future
promise.success(100)
promise.future.value
```

### 7 Dealing with Future Failures
```
val failedFuture = Future{10/0}
failedFuture.value
val failedException = failedFuture.failed
```

