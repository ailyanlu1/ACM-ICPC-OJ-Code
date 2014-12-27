# 2010 World Finals: Tracking Bio-bots
## Solution

虽然题目的方格的范围很大，但是由于墙的数目只有1000个，因此产生的在X方向和Y方向坐标值不会超过2000个。 因此可以先离散化，然后把墙的情况填充到一个数组里面。如SAMPLE离散化后得到的图形如下：

<pre>
00000
01110
00000
00100
00000
00001
00000
</pre>

从右上角Exit点开始，使用简单的DP，就可以在两重循环里面判断出那些格子是Exit点可以到达的，那些是不可以的。最后再进行统计那些既不能 到达，也不是墙的格子的实际大小即可。

注意墙有可能堵住出口