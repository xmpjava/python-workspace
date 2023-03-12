```
from collections import Counter

import pandas as pd

df = pd.read_excel('xxx.xlsx', sheet_name='Sheet1')

# 定义要查找的关键词
keywords = ['一般','尚可','够用','完美','行','降噪','纯','净','杂音','噪音','佳','差','糟糕','难听','烂','中规中矩','普通','动听','悦耳','平衡','少','过量','局促','厚','薄','不足','力','亮','暗','松','尖','柔','层次','饱和','真实','失真','坚实','圆润','软','硬','浑浊','粗','炸','细','毛','沙','破','闷','脆','立体','空间','漏音']

# 创建一个空字典来存储每个关键词的出现次数
counts = {}

# 遍历所有单元格，查找包含关键词的单元格，并增加对应的计数器
for row_index, row in df.iterrows():
    for col_index, value in enumerate(row):
        for keyword in keywords:
            if keyword in str(value):
                if keyword in counts:
                    counts[keyword] += 1
                else:
                    counts[keyword] = 1

# 输出每个关键词的出现次数
for keyword, count in counts.items():
    print(f'关键词 "{keyword}" 在单元格中出现了 {count} 次')

# 将keywords中的关键词作为列名，counts中的计数作为值，创建一个新的EXCEL表格
df = pd.DataFrame([counts], columns=keywords)
df.to_excel('关键词统计.xlsx', index=False)
```