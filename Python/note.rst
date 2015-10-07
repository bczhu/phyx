.. _Python_学习:

Python 学习
=================

#. **数组初始化**

.. sourcecode:: python

   #初始化一维数组
   p1=[1]*100

   #初始化二维数组100*10
   p2=[[1] * 100 for i in xrange(10)]
   #Below does not work!
   p2=[[1] * 100]*10
   #Or we can use:
   p2=[[None for col in range(100)] for row in range(10)]

   #初始化三维维数组2*3*4
   p3=[[[1] * 2 for i in xrange(3)] for j in xrange(4)]
   #Or
   p3=[[[1 for i in xrange(2)] for j in xrange(3)] for k in xrange(4)]
   #Or
   p3=[]
   for i in range(2):
       p3.append([])
       for j in range(3):
           p3[i].append([])
           for k in range(4):
               p3[i][j].append(0)

#. python 中的内积 ``dot`` 是没有复共轭的，``vdot`` 有，而matlab ``dot(a,b)`` 是对a取复共轭的。
