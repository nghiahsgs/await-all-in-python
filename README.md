# await-all-in-python
await all in python


```python
import asyncio
import time

async def bar(i):
  print('started', i)
  await asyncio.sleep(1)
  print('finished', i)
  return i

async def main():
  results = await asyncio.gather(*[bar(i) for i in range(10)])
  print(results)


t1 = time.time()
loop = asyncio.get_event_loop()
loop.run_until_complete(main())
loop.close()
t2 = time.time()
print("time delta",t2-t1)
```
