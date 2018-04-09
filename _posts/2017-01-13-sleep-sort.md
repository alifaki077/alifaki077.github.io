---
layout: post
title: خوارزمية sleep sort
---

إذا كنت قد درست خوارزميات الترتيب من قبل فأن هذه الأسماء مألوفة لك bubble sort , selection sort, merge sort, quick sort وغيرهم.

هذه الخوارزميات تركز على الكفائة efficiency أي أن الخوارزمية تكون أفضل كلما قل وقت تنفيذها وقل إستهلاكها للذاكرة.

هناك خوارزميات أخرى تخالف هذا المبدأ تماماً مثل sleep sort . هذه الخوارزميات ليس الهدف إستخدامها في البرامج الحقيقية ولكن هي لإكتشاف الأفكار المختلفة وللتسلية أيضاً.

sleep sort هي خوارزمية ترتيب تقوم بإنشاء مسلك thread لكل عنصر من عناصر المصفوفة المراد ترتيبها هذا ال thread يقوم بالنوم بمقدار قيمة العنصر ثم يطبع العنصر.

مثلاً لو كان لدينا المصفوفة [5, 3, 7] فإن ال thread  الأول به العنصر 7 لذا سينام 7 ثواني وبعدها يطبع 7 و هكذا بالنسبة لباقي عناصر المصفوفة.

هذا تطبيق الخوارزمية بلغة بايثون بإستخدام  ال processes بدل ال threads


```python
from multiprocessing import Process
from time import sleep

items = [4, 1, 2, 5, 7]


def sleep_sort(i):
    sleep(i)
    print(i, end=", ")

for i in items:
    p = Process(target=sleep_sort, args=(i,))
    p.start()
    
```