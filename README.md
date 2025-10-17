# Pagina-o
LRU/FIFO/MRU

FIFO:


Remove a página que está há mais tempo na memória.

Funcionamento:


-Segue o princípio básico de uma fila convencional

-A primeira página a entrar será a primeira a sair

-Não considera frequência ou tempo de acesso das páginas

-A ordem de chegada determina a ordem de saída

Explicação do código:

-Usa uma lista comum como memória

-Quando a memória enche  remove sempre o primeiro elemento (pop(0))

-Páginas novas são adicionadas no final (append())

-Se a página já existe não faz nada


LRU:


Remove a página que não é acessada há mais tempo.

Funcionamento:


-Mantém um registro da ordem de acesso das páginas

-Páginas acessadas recentemente são consideradas "mais importantes"

-Páginas não acessadas há muito tempo são candidatas a remoção

-Sempre remove a página que está há mais tempo sem ser acessada


Explicação do código:

-Usa OrderedDict para controlar a ordem de acesso

-Quando a memória enche remove o primeiro item (popitem(last=False)) o menos recente

-Se a página já existe  move para o final com move_to_end(p) ou seja fica como mais recente

-Páginas novas são adicionadas como mais recentes


MRU:

Remove a página que foi acessada mais recentemente.

Funcionamento:



-Baseia-se na ideia de que páginas recentemente usadas podem não ser necessárias novamente em breve

-Atualiza a ordem das páginas a cada acesso

-Prioriza a manutenção de páginas que não foram acessadas recentemente

-Contrário à intuição comum de cache


Explicação do código:

-Usa uma lista comum como memória

-Quando a memória enche  remove o último elemento (pop(-1))  o mais recente

-Se a página já existe  remove ela e coloca no final ou seja atualiza como mais recente

-Páginas novas vão para o final


