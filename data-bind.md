数据绑定
| 格式| 描述 |
|:---:|:----:|
| [target]="expr" | 单向数据绑定 expr > target |
| {{ expr }} | 字符串单向绑定 |
| (target)= "expr" | 事件处理单向绑定 target > expr |
| [(target)] = "expr" | 双向数据绑定 |

如果绑定的目标与任何指令都不匹配，则尝试应用属性绑定。常见的属性绑定有标准属性绑定和元素属性绑定。
