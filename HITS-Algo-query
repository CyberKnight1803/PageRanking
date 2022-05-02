import networkx as nx

def get_successors(i):
    succ_edges = list(filter(lambda x: x[0] == i, web_graph.edges))
    successors = [i[1] for i in succ_edges]
    return successors

def get_predecessors(i):
    pred_edges = list(filter(lambda x: x[1] == i, web_graph.edges))
    predecessors = [i[0] for i in pred_edges]
    return predecessors

web_graph = nx.read_gpickle("web_graph.gpickle")
web_graph

query = 'time'
keywords = query.lower().split()
keywords

no_of_files = len(web_graph)
nodes_satisfing_query = []

for i in range(no_of_files):
    content = web_graph.nodes[i]['page_content'].lower()
    bool = True
    for word in keywords:
        if word not in content:
            bool = False
            break
    if bool:
        nodes_satisfing_query.append(i)

print('nodes_satisfing_query:', nodes_satisfing_query)

nodes = set(nodes_satisfing_query)
# print(nodes_satisfing_query)
for node in nodes_satisfing_query:
    # print(get_predecessors(node))
    nodes.update(get_predecessors(node))
    # print(get_successors(node))
    nodes.update(get_successors(node))

nodes = list(nodes)
len(nodes)

adj = []
new = []
for i in range(len(nodes)):
    for j in range(len(nodes)):
        if nodes[j] in get_successors(nodes[i]):
            new.append(1)
        else:
            new.append(0)
    adj.append(new)
    new = []

for i in adj:
    print(i)