sync.Map的核心实现 - 两个map，一个用于写，另一个用于读，这样的设计思想可以类比缓存与数据库
sync.Map的局限性 - 如果写远高于读，dirty->readOnly 这个类似于 刷数据 的频率就比较高，不如直接用 mutex + map 的组合
sync.Map的设计思想 - 保证高频读的无锁结构、空间换时间