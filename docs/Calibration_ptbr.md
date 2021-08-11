# Calibração

>A inclinação do iSpindle no mosto pode ser convertida em graus Plato (ºPlato), densidade (SG) ou outras unidades. Para isso, deve ser feita uma referência entre os graus de inclinação do iSpindle e a unidade escolhida. Os valores de referência terão que ser medidos e com o uso de uma tabela do Excel é feito um gráfico e uma fórmula. O Excel calculará a relação entre a inclinação do iSpindle e os graus, densidade ou outros do iSpindle. Como cada iSpindle auto-construído será diferente, a medição de referência é necessária para cada iSpindle individual, mas apenas uma vez.

***

# Conteúdo
- [Método Fácil (I)](#easy-method-(I))
- [Método melhorado usando fermentação rápida (II)](#improved-method-using-fast-fermenting-(II))
- [Formula Excel tabel](#formula)

***

## Easy method (I)

É recomendado conectar o iSpindel com [Ubidots](https://ubidots.com/) para facilitar a leitura das inclinações medidas. Além disso, é sábio alterar as configurações do iSpindel para que ele envie novas leituras a cada 21 segundos. Com um intervalo tão curto, as medições podem ser facilmente seguidas no site do [Ubidots](https://ubidots.com/).

1. Colocar o iSpindel em água limpa (0 graus Plato, SG 1.000).
> ***Anote a inclinação do iSpindel

2. Faça uma solução de açúcar na água com a maior densidade prevista. Se você estiver preparando cervejas fortes com uma alta densidade inicial, você deve ter medidas de referência nesta faixa. Para a maioria das cervejeiros, uma solução com uma densidade em torno de 1,085 ou cerca de 20 graus Plato serve.
> *Exemplo para solução açúcar: 400 ml com 100 g de açúcar
> ***Medir a densidade ou os graus Plato e anotar com a inclinação do iSpindel***

3. Diluir a solução acima com água até atingir 15 graus Platão ou densidade 1,061
> *Exemplo para solução de açúcar: diluir a solução do ponto 2 com 166 ml de água
> ***Medir a densidade ou os graus Plato e anotar com a inclinação do iSpindel***

4. Diluir a solução do ponto acima até atingir aproximadamente 10 graus Plato, SG 1.040 de 10 graus Brix.
>*Exemplo: Diluir a solução a partir do ponto 3 com 333 ml de água.

>***Medir a densidade ou os graus Plato e anotar com a inclinação do iSpindel***

5. Diluir a solução do ponto acima até atingir aproximadamente 7,5 graus Platão, SG 1.030 ou 7,5 graus Brix.
>*Exemplo: Diluir a solução a partir do ponto 4 com 333 ml de água.

>***Medir a densidade ou os graus Plato e anotar com a inclinação do iSpindel***

6. Diluir a solução do ponto acima até atingir aproximadamente 5 graus Platão, SG 1.020 ou 5 graus Brix
>*Exemplo: Diluir a solução a partir do ponto 5 com 666 ml de água

>***Medir a densidade ou os graus Plato e anotar com a inclinação do iSpindel***

7. Diluir a solução do ponto acima até atingir aproximadamente 2,5 graus Platão, SG 1,010 ou 2,5 graus Brix.
>Exemplo: Diluir a solução a partir do ponto 6 com 2000 ml de água.
>Meça a densidade ou os graus Plato e anote-a com a inclinação do iSpindel
>Digite os pontos medidos na planilha Excel (veja abaixo). Esta planilha Excel calculará a fórmula para a referência
 
## Método melhorado usando fermentação rápida (II)

Este método é mais preciso, pois levará em conta o efeito do CO2 formado durante a fermentação.

É recomendado conectar o iSpindel com [Ubidots](https://ubidots.com/) para facilitar a leitura das inclinações medidas. Além disso, é sábio alterar as configurações do iSpindel para que ele envie novas leituras a cada 20 segundos. Com um intervalo tão curto, as medições podem ser facilmente seguidas no site do [Ubidots](https://ubidots.com/).

1. Colocar o iSpindel em água limpa (torneira) (0º Platão ou SG 1.000)
>***Anote a inclinação medida do iSpindel***

2. Faça uma solução de açúcar na água com a maior densidade prevista. Se você estiver preparando cervejas fortes com uma alta densidade inicial, você deve ter medidas de referência nesta alta faixa. Para a maioria, uma solução com uma densidade em torno de 1,085 ou cerca de 20 graus Platão serve.
>*Exemplo: 800 ml de água + 200 g de açúcar cristal.*

3. Adicione levedura à solução de açúcar e deixe o iSpindel flutuar na solução
>***Medir a densidade ou os graus Plato e anotar com a inclinação do iSpindel***

4. Medir a densidade do fluido e a inclinação correspondente do iSpindle em intervalos regulares até que o final da fermentação tenha sido alcançado.
>***Digite os valores medidos na planilha Excel. Esta folha mostrará a fórmula da curva de calibração.***
>
>****Cautela: se você medir em valor Brix com um refratômetro, você tem que recalcular o valor medido para corrigir para a leitura de álcool***

***

# Formula

- ## [Ferramenta de Calibração por Gravidade Online](http://www.ispindel.de/tools/calibration/calibration.htm)

Os valores medidos podem ser inseridos no campo SG/Plato ou BRIX mais a inclinação correspondente. Ele calculará uma fórmula de 2º ou 3º grau que prediz a densidade ou os graus de Platão dado um valor de inclinação. Esta fórmula deve ser inserida no Firmware para poder obter leituras em densidade ou graus de Plato.

***

- ## Planilha do Excel

Os valores medidos podem ser inseridos na planilha Excel. Esta folha calculará uma fórmula que preverá a densidade ou os graus de Platão dado um valor de inclinação. Esta fórmula deve ser inserida no Firmware para poder obter leituras em densidade ou graus de Platão. Outras leituras, tais como atenuação aparente ou % de álcool podem ser obtidas de maneiras semelhantes com o uso de uma 'Variável Derivada' em [Ubidots](https://ubidots.com/).

1. Primeiro digite os valores medidos no Excel:    
[Baixar tabela Excel](https://github.com/universam1/iSpindel/blob/master/docs/Kalibrierung_en.xlsm)
2. Comece a macro **Atualização da fórmula** clicando no botão. A fórmula será atualizada.     
![Excelcalc](/pics/Excelcalc.jpg)
3. Na conta de [Ubidots](https://ubidots.com/) uma **Variável derivada** tem que ser adicionada. Esta é uma variável que é calculada com outras variáveis como fonte. Isto pode ser feito seguindo os próximos passos.
4. Em [Ubidots](https://ubidots.com/) vá para **Source**
5. Escolha iSpindel como fonte
6. Clique em **(+) Adicionar variável**
7. Escolha **Derivado**
![Derivado](/pics/Ubiderived.jpg)
8. Agora você pode preencher a fórmula a partir do Excel. As peças da fórmula mostradas como ***(tilt)*** têm que ser substituídas. Para fazer isso, clique em ***insert variável*** e escolha **tilt**. Dê um nome que faça sentido para a variável recém-criada, ou seja, Densidade ou Plato
9. Em **Dashboard** você pode criar apresentações gráficas de seus dados.
