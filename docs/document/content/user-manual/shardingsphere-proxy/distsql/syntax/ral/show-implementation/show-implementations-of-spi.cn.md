+++
title = "SHOW PLUGINS OF SPI"
weight = 7
+++

### 描述

`SHOW PLUGINS OF pluginClass` 语法用于查询指定的 `SPI` 接口所有具体的实现类。

### 语法

{{< tabs >}}
{{% tab name="语法" %}}
```sql
showPluginImplementations ::=
  'SHOW' 'PLUGINS' 'OF' pluginClass

pluginClass ::=
  string
```
{{% /tab %}}
{{% tab name="铁路图" %}}
<iframe frameborder="0" name="diagram" id="diagram" width="100%" height="100%"></iframe>
{{% /tab %}}
{{< /tabs >}}

### 返回值说明

| 列            | 说明     |
|--------------|--------|
| type         | 类型     |
| type_aliases | 类型别名   |
| description  | 描述     |

### 示例

- 查询 `org.apache.shardingsphere.sharding.spi.ShardingAlgorithm` 接口的所有实现类

```sql
SHOW PLUGINS OF 'org.apache.shardingsphere.sharding.spi.ShardingAlgorithm'
```

```sql
SHOW PLUGINS OF 'org.apache.shardingsphere.sharding.spi.ShardingAlgorithm';
+----------------+--------------+-------------+
| type           | type_aliases | description |
+----------------+--------------+-------------+
| MOD            |              |             |
| HASH_MOD       |              |             |
| VOLUME_RANGE   |              |             |
| BOUNDARY_RANGE |              |             |
| AUTO_INTERVAL  |              |             |
| INTERVAL       |              |             |
| CLASS_BASED    |              |             |
| INLINE         |              |             |
| COMPLEX_INLINE |              |             |
| HINT_INLINE    |              |             |
+----------------+--------------+-------------+
10 rows in set (0.52 sec)
```

### 补充说明

针对一些常用的 `SPI` 接口实现，ShardingSphere 提供了语法糖功能，可以简化操作，目前已提供的语法糖功能的 `SPI` 接口如下：

- 查询 `org.apache.shardingsphere.sharding.spi.ShardingAlgorithm` 接口实现：[SHOW SHARDING ALGORITHM PLUGINS](/cn/user-manual/shardingsphere-proxy/distsql/syntax/ral/show-implementation/sharding/show-sharding-algorithm-implementations)
- 查询 `org.apache.shardingsphere.readwritesplitting.spi.ReadQueryLoadBalanceAlgorithm` 接口实现：[SHOW READ QUERY LOAD BALANCE ALGORITHM PLUGINS](/cn/user-manual/shardingsphere-proxy/distsql/syntax/ral/show-implementation/readwrite-splitting/show-read-query-load-balance-algorithm-implementations)
- 查询 `org.apache.shardingsphere.encrypt.spi.EncryptAlgorithm` 接口实现：[SHOW ENCRYPT ALGORITHM PLUGINS](/cn/user-manual/shardingsphere-proxy/distsql/syntax/ral/show-implementation/encrypt/show-encrypt-algorithm-implementations)
- 查询 `org.apache.shardingsphere.mask.spi.MaskAlgorithm` 接口实现：[SHOW MASK ALGORITHM PLUGINS](/cn/user-manual/shardingsphere-proxy/distsql/syntax/ral/show-implementation/mask/show-mask-algorithm-implementations)
- 查询 `org.apache.shardingsphere.shadow.spi.ShadowAlgorithm` 接口实现：[SHOW SHADOW ALGORITHM PLUGINS](/cn/user-manual/shardingsphere-proxy/distsql/syntax/ral/show-implementation/shadow/show-shadow-algorithm-implementations)
- 查询 `org.apache.shardingsphere.keygen.core.algorithm.KeyGenerateAlgorithm` 接口实现：[SHOW KEY GENERATE ALGORITHM PLUGINS](/cn/user-manual/shardingsphere-proxy/distsql/syntax/ral/show-implementation/show-key-generate-algorithm-implementations)

### 保留字

`SHOW`、`PLUGINS`、`OF`

### 相关链接

- [保留字](/cn/user-manual/shardingsphere-proxy/distsql/syntax/reserved-word/)
