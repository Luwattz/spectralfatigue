Ferramentas na Analise de Fadiga Estocastica em Estruturas Mecanicas

Arquivos:

spectrallife.m		estima vida de um ponto a partir do psd de tensoes
spectralfatigue.m	estima vida de um ponto a partir de um sinal temporal de tensoes
Ncycles.m		dada uma tabela representando a curva SN de um material, retorna o numero de ciclos para falha para um valor de amplitude

Exemplos:

fatiguelifeexamples.m	time series examples
exemplo2nCode.m		psd input example

###### Funcao spectralfatigue.m ######

		T = spectralfatigue( sinal, sn, criteria, pdf, showplots)
T:
	Tempo estimado ate falha.
sinal:
	Estrutura contendo:
		sinal.t: vetor de tempo em s.
		sinal.ext: vetor de tensoes em MPa.
sn:
	Dados usados para interpolar a curva S-N. duas colunas:
		primeira coluna: numero de ciclos (N [ciclos])
		segunda coluna: amplitude do ciclo de tensao (S [MPa])
criteria:
	Correcao da curva S-N para considerar valores medios
		criteria = 1	Goodman
		criteria = 2	Gerber
		criteria = 3	Sem correcao
pdf:
	Escolher um estimador para a funcao densidade de probabilidade:
		PDF de Dirlik: pdf = 'dirlik'
		PDF de Rayleigh: pdf = 'rayleigh'
		PDF de Gauss: pdf = 'gauss'
		PDF de processo de banda estreita: pdf = 'narrow'
showplots:
	Mostrar graficos (Amostra do sinal, PSD, Curva S-N, PDF):
		showplots = 0	nao mostra graficos
		showplots = 1	mostra graficos

###### Funcao spectrallife.m ######

		T = spectrallife( psd, sn, meanstress, criteria, pdf, showplots)
T:
	Tempo estimado ate falha.
psd:
	Matriz com duas colunas:
		primeira coluna: frequencias
		segunda coluna: psd de tensoes no ponto de interesse
sn:
	Dados usados para interpolar a curva S-N. duas colunas:
		primeira coluna: numero de ciclos (N [ciclos])
		segunda coluna: amplitude do ciclo de tensao (S [MPa])
meanstress:
	Valor medio de tensao para correcao da curva SN.
criteria:
	Correcao da curva S-N para considerar valores medios
		criteria = 1	Goodman
		criteria = 2	Gerber
		criteria = 3	Sem correcao
pdf:
	Escolher um estimador para a funcao densidade de probabilidade:
		PDF de Dirlik: pdf = 'dirlik'
		PDF de Rayleigh: pdf = 'rayleigh'
		PDF de Gauss: pdf = 'gauss'
		PDF de processo de banda estreita: pdf = 'narrow'
showplots:
	Mostrar graficos (PSD, Curva S-N, PDF):
		showplots = 0	nao mostra graficos
		showplots = 1	mostra graficos

