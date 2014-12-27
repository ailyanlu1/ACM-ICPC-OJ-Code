# 2008 World Finals: Steam Roller

使用最短路算法解决该问题。

由于刹车前后的道路，以及启动后、终止前的道路的耗费的时间都要加倍，因此需要有恰当的状态表示方法，以免某些道路的加倍被重复计算。最短 路使用状态：dis[issame][direction][pt]表示，意思是当前点为Pt，进入pt的方向为dir，前两条步的方向是否相同为 issame的情况下，到达pt前一点pp的最短路。之所以这样表示状态，是因为pp是否按双倍计算是不知道的。选择当前点的前进方向，会影响之前的时间 （如果转弯，上一段路的时间就要加倍）。如果不加以记录，有可能会重复计算。对于当前的状态，如果issame为false，或当前dir与下一个dir 不一致，都要将pp到pt这一段路的距离双倍计算。

注意起始点与终点的处理。尤其是到达终点，必须进行统计最优值，而不能马上退出。而且到达终点后有可能继续走，再返回终点，会得到更优的答案，要稍加注意。 