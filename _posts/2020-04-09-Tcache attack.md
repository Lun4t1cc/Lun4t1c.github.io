## tcache dup

因为 tcache 的检查十分宽松，所以可以对同一个 chunk 进行连续两次 free。之后再通过一次 malloc 申请出 free 掉的 chunk，打印其内容，即可泄露堆地址。

## tcache perthread corruption

- 控制 tcache_perthread_struct 后，通过 overwrite 制造 Tcachebins 已满的假象，再 free 一个 chunk，该 chunk 便会直接进入对应的 bins 中