# Análise exploratória de dados utilizando dados da segurança pública do Estado do Rio de Janeiro.

### dados utilizados:
* http://www.ispdados.rj.gov.br/Arquivos/BaseMunicipioMensal.csv

### Objetivo:
* Realizar a carga e transformação(se necessário) dos dados utilizando o pandas, e tentar tirar algumas informações dos dados.

# Atributos:
### Descrição das colunas do DataFrame(df)
None da coluna | Descrição | Contagem | Observação
--------- | ------ | ------ | ------
fmun_cod | Código IBGE de 7 dígitos do município
fmun | Nome do município
ano | Ano da comunicação da ocorrência
mes | Mês da comunicação da ocorrência
mes_ano | Mês e ano da comunicação da ocorrência
regiao | 1-Baixada / 2-Capital / 3-Grande Niterói / 4-Interior
fase | 2-Consolidado sem errata / 3-Consolidado com errata
hom_doloso | Homicídio doloso | vítima
lesao_corp_morte | Lesão corporal seguida de morte | vítima
latrocinio | Latrocínio (roubo seguido de morte) | vítima
cvli | Crimes Violentos Letais Intencionais | vítima | Homicídio doloso + Lesão corporal seguida de morte + Latrocínio
hom_por_interv_policial | Morte por intervenção de agente do Estado | vítima
letalidade_violenta | Letalidade violenta | vítima | Homicídio doloso + Lesão corporal seguida de morte + Latrocínio + Morte por intervenção de agente do Estado
tentat_hom | Tentativa de homicídio | vítima
lesao_corp_dolosa | Lesão corporal dolosa | vítima
estupro | Estupro | vítima | "Em 2009, o Artigo 214 do Código Penal passou a caracterizar Atentado Violento ao Pudor (AVP) como Estupro. Por isso, antes de 2009, a variável ""estupro"" é na verdade a soma de ""estupro"" e ""AVP""."
hom_culposo | Homicídio culposo (trânsito) | vítima | Atropelamento + colisão + outros
lesao_corp_culposa | Lesão corporal culposa (trânsito) | vítima |Atropelamento + colisão + outros
roubo_transeunte | Roubo a transeunte | caso
roubo_celular | Roubo de telefone celular | caso
roubo_em_coletivo | Roubo em coletivo | caso
roubo_rua | Roubo de Rua | caso |Roubo a transeunte + Roubo de celular + Roubo em coletivo
roubo_veiculo | Roubo de veículo | caso
roubo_carga | Roubo de carga | caso
roubo_comercio | Roubo a estabelecimento comercial | caso
roubo_residencia | Roubo a residência | caso
roubo_banco | Roubo a banco | caso
roubo_cx_eletronico | Roubo de caixa eletrônico | caso
roubo_conducao_saque | Roubo com condução da vítima para saque em instituição financeira | caso
roubo_apos_saque | Roubo após saque em instituição financeira | caso
roubo_bicicleta | Roubo de bicicleta | caso
outros_roubos | Outros roubos que não os listados acima | caso | Inclui contagem de ocorrências de latrocínio
total_roubos | Total de roubos | caso | Soma de todos os roubos listados acima
furto_veiculos | Furto de veículo | caso
furto_transeunte | Furto a transeunte | caso
furto_coletivo | Furto em coletivo | caso
furto_celular | Furto de telefone celular | caso
furto_bicicleta | Furto de bicicleta | caso
outros_furtos | Outros furtos que não os listados acima | caso
total_furtos | Total de furtos | caso | Soma de todos os furtos listados acima
sequestro | Extorsão mediante sequestro (sequestro clássico) | vítima
extorsao | Extorsão | caso
sequestro_relampago | Extorsão com momentânea privação da liberdade (sequestro relâmpago) | vítima
estelionato | Estelionato | caso
apreensao_drogas | Apreensão de drogas | caso | Refere-se à aglutinação dos títulos de Uso/Porte, Tráfico e Apreensão de substância entorpecente
posse_drogas | Número de registros que possuem algum título referente a posse de drogas | caso | A soma dessas variáveis pode ser maior que o número de registros de apreensão de drogas, pois um mesmo registro pode conter mais de um tipo de apreensão de drogas.
trafico_drogas | Número de registros que possuem algum título referente a tráfico de drogas | caso 
apreensao_drogas_sem_autor | Número de registros que possuem algum título referente a apreensão de drogas sem autor | caso
recuperacao_veiculos | Recuperação de veículo | caso | Refere-se à recuperação de veículos, não necessariamente roubados/furtados durante o mês, e/ou roubados/furtados na mesma área.
apf | Auto de Prisão em Flagrante | autor
aaapai | Auto de Apreensão de Adolescente por Prática de Ato Infracional | adolescente infrator
cmp | Cumprimento de Mandado de Prisão | autor 
cmba | Cumprimento de Mandado de Busca e Apreensão | adolescente infrator
ameaca | Ameaça | vítima
pessoas_desaparecidas | Pessoas desaparecidas | vítima
encontro_cadaver | Encontro de cadáver | vítima
encontro_ossada | Encontro de ossada | vítima
pol_militares_mortos_serv | Policiais Militares mortos em serviço | vítima
pol_civis_mortos_serv | Policiais Civis mortos em serviço | vítima
registro_ocorrencias | Registro de ocorrências | caso | Total de registros de ocorrências divulgados no mês