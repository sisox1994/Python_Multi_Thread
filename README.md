# Thread 

兩個Thread 分別同時執行

```python
import threading
import time


def Master():

    print("<Master ID>:", threading.get_ident())
    cnt = 3
    while cnt > 0:
        print("[master]-------------", cnt)
        time.sleep(1.0)
        cnt -= 1


def Sub():

    print("<Sub ID>:", threading.get_ident())
    cnt = 5
    while cnt > 0:
        print("[sub]", cnt)
        time.sleep(1.0)
        cnt -= 1


if __name__ == "__main__":

    print("<Main ID>:", threading.get_ident())
    t1 = threading.Thread(target=Master)
    t2 = threading.Thread(target=Sub)

    t1.start()
    t2.start()
```

