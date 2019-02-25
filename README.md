# 小工具

## 背景

操作类工作均有规律可寻，员工按照“操作手册”即可完成工作。其中一些工作内容逻辑清晰，规则健全，若配合 IT 技术，可实现自动化。

本仓库为方便工作开发的各种小工具，将重复性工作、人工操作效率低、易出错的工作，用 IT 技术辅助来完成。每个工具均可实现某项工作全自动或半自动作业，实现 IT 换人。这将大大提高效率，减少员工机械重复的工作，减少人工失误，让员工将时间精力投入到其他工作中，实现降本增效。

## 目标

- 傻瓜式操作，一键运行或输入变量即可得到结果
- 适配多种场景，易扩展
- 效率高、准确性高、用户体验好

## 一致性检查工具

简单概括需求，就是 1 个原始数据，2 个需要对比的数据，3 个表格均为 excel 文件，表的格式、包含的字段、字段的标题都不相同，但是字段标题存在某种对应关系或计算关系，现需要对多个字段进行一致性对比。理想情况想要的结果是能知道哪些行不一致，具体不一致的内容是哪一列，特点是数据量大，需要经常对比。[使用说明](https://github.com/thianda/tools-ip-contrast) 

**实现思路**

1. 整理原始数据：剔除无用数据列、筛选掉无效的行，准确识别字段的标题
2. 对比并标记不一致。
3. 生成友好的适合人阅读的结果

## IPv6 地址拆分工具

目前处于设计阶段，具体实现的需求详见 [这里](https://github.com/thianda/tools-ipv6-split/)。

## 城域网设备 vlan 统计

**基本思路**

1. 采集各 bras 的 `vpn-instance LNTL_PON_Manager_HW`和`vpn-instance LNTL_PON_Manager_ZTE`的`ip routing-table`信息
2. 基于`ip`匹配 OLT 名称与`bras`、`Trunk`口信息的关系
3. 梳理现网`Trunk`口的子接口数据
4. 自动生成新增`svlan`脚本 

```sh
ping -vpn-instance LNTL_PON_Manager_HW  10.61.209.98
dis access-user vpn-instance LNTL_PON_Manager_HW
dis ip routing-table vpn-instance LNTL_PON_Manager_HW 10.61.211.84
```

