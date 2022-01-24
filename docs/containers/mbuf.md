# rte_mbuf

源码目录：src/lib/librte_mbuf


## 宏定义

### #define RTE_PKTMBUF_POOL_F_PINNED_EXT_BUF  (1 << 0) 

#### 参数

​	无

#### 释义

一个标记，当内存池存在这个标记时，

#### 关联源码





### #define __rte_mbuf_sanity_check(m, is_h) 

#### 参数

1. **m** 要检查的mbuf地址
2. **is_h** 是否是mbuf最开始的段

#### 释义

在开启调试模式的情况下检查 mbuf的正确性，如果没有开启调试模式则不做任何事情 。当定义宏**RTE_LIBRTE_MBUF_DEBUG**时打开调试模式，系统将调用<a href="#rte_mbuf_sanity_check">rte_mbuf_sanity_check</a>函数对mbuf进行检查。

#### 关联源码

源码地址：src/lib/librte_mbuf/rte_mbuf.h[329行]

```shell
 #ifdef RTE_LIBRTE_MBUF_DEBUG
 	#define __rte_mbuf_sanity_check(m, is_h) rte_mbuf_sanity_check(m, is_h)
 #else /*  RTE_LIBRTE_MBUF_DEBUG */
	 #define __rte_mbuf_sanity_check(m, is_h) do { } while (0)
 #endif /*  RTE_LIBRTE_MBUF_DEBUG */
```

## 方法定义

#### <a name="rte_mbuf_sanity_check">rte_mbuf_sanity_check </a>

void rte_mbuf_sanity_check (const struct rte_mbuf *m, int is_header)

