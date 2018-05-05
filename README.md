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
