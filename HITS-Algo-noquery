import numpy as np

def update_authority(L, u):
    v_ = L.T @ u
    v = v_/sum(v_)
    return v

def update_hub(L, v):
    u_ = (L @ v)
    u = u_/sum(u_)
    return u

def read_adj():
    adj = []
    with open('adj.txt') as f:
        lines = f.readlines()
        for line in lines:
            adj.append(list(map(int, line.split())))
        
    return np.array(adj)

def get_rank_by_auth(v):
    sorted_by_auth = {}
    for i in range(len(v)):
        sorted_by_auth[v[i]] = i

    for i in sorted (sorted_by_auth.keys()):
        print(sorted_by_auth[i], end = " ")
    
    print()

def get_rank_by_hub(u):
    sorted_by_hub = {}
    for i in range(len(u)):
        sorted_by_hub[u[i]] = i
    
    for i in sorted (sorted_by_hub.keys()):
        print(sorted_by_hub[i], end = " ")
    print()

if __name__ == "__main__":
    adj = read_adj()
    L = adj
    u = len(adj)*[1]

    for i in range(100000):
        v = update_authority(L, u)
        u = update_hub(L, v)
    # if i%100 == 0:
    #     print(i)
    #     print("AUTH:", v)
    #     print("HUB:", u)

    print("AUTH:", v)
    print("HUB:", u)

    get_rank_by_auth(v)
    get_rank_by_hub(u)