import matplotlib.pyplot as plt
import networkx as nx

# 创建图
G = nx.DiGraph()

# 定义节点
G.add_node("解表药", color='lightblue')
G.add_node("发汗", color='green')
G.add_node("退热", color='green')
G.add_node("止咳", color='green')
G.add_node("抗病毒", color='green')
G.add_node("提升免疫力", color='green')

# 定义作用机制
G.add_node("刺激汗腺分泌", color='yellow')
G.add_node("促进热量散发", color='yellow')
G.add_node("扩张气道", color='yellow')
G.add_node("抑制病毒复制", color='yellow')
G.add_node("激活免疫细胞", color='yellow')

# 添加边
G.add_edges_from([
    ("解表药", "发汗"),
    ("发汗", "刺激汗腺分泌"),
    ("刺激汗腺分泌", "促进热量散发"),
    ("解表药", "退热"),
    ("退热", "促进热量散发"),
    ("解表药", "止咳"),
    ("止咳", "扩张气道"),
    ("解表药", "抗病毒"),
    ("抗病毒", "抑制病毒复制"),
    ("解表药", "提升免疫力"),
    ("提升免疫力", "激活免疫细胞")
])

# 绘制图
pos = nx.spring_layout(G)
nx.draw(G, pos, with_labels=True, node_color='lightblue', edge_color='gray', node_size=3000, font_size=10, font_color='black')
plt.show()
