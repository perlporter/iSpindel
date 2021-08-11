# Calibração

>A inclinação do iSpindle no mosto pode ser convertida em graus Plato (ºPlato), densidade (SG) ou outras unidades. Para isso, deve ser feita uma referência entre os graus de inclinação do iSpindle e a unidade escolhida. Os valores de referência terão que ser medidos e com o uso de uma tabela do Excel é feito um gráfico e uma fórmula. O Excel calculará a relação entre a inclinação do iSpindle e os graus, densidade ou outros do iSpindle. Como cada iSpindle auto-construído será diferente, a medição de referência é necessária para cada iSpindle individual, mas apenas uma vez.


# Conteúdo
- [Easy method (I)](#easy-method-(I))
- [Improved method using fast fermenting (II)](#improved-method-using-fast-fermenting-(II))
- [Formula Excel tabel](#formula)

***

## Easy method (I)

É recomendado conectar o iSpindel com [Ubidots](https://ubidots.com/) para facilitar a leitura das inclinações medidas. Além disso, é sábio alterar as configurações do iSpindel para que ele envie novas leituras a cada 20 segundos. Com um intervalo tão curto, as medições podem ser facilmente seguidas no site do [Ubidots](https://ubidots.com/).

1. Put the iSpindel in clean water (0 degrees Plato, SG 1.000).   
> ***Write down the tilt of the iSpindel***

2. Make a solution of sugar in water with the highest anticipated density. If you are brewing strong beers with a high starting density, you should have reference measurements in this high range. For most brewers a solution with a density around 1.085 or around 20 degrees Plato will do.      
> *Example for sugar solution: 400 ml with 100 g sugar*     
> ***Measure the density or the degrees Plato and write it down with the tilt of the iSpindel***

3. Dilute the solution above with water until it reaches 15 degrees Plato or density 1.061       
>*Example for sugar solution: dilute the solution of point 2 with 166 ml of water*     
>***Measure the density or the degrees Plato and write it down with the tilt of the iSpindel***        

4. Dilute the solution from the point above till it reaches approximately 10 degrees Plato, SG 1.040 of 10 degrees Brix.       
>*Example: Dilute the solution from point 3 with 333 ml of water.*        
>***Measure the density or the degrees Plato and write it down with the tilt of the iSpindel***     

5. Dilute the solution from the point above till it reaches approximately 7.5 degrees Plato, SG 1.030 or 7.5 degrees Brix.
>*Example: Dilute the solution from point 4 with 333 ml of water.*        
>***Measure the density or the degrees Plato and write it down with the tilt of the iSpindel***     

6. Dilute the solution from the point above till it reaches approximately 5 degrees Plato, SG 1.020 or 5 degrees Brix
>*Example: Dilute the solution from point 5 with 666 ml of water*        
>***Measure the density or the degrees Plato and write it down with the tilt of the iSpindel***   

7. Dilute the solution from the point above till it reaches approximately 2.5 degrees Plato, SG 1.010 or 2.5 degrees Brix.     
>*Example: Dilute the solution from point 6 with 2000 ml of water.*      
>***Measure the density or the degrees Plato and write it down with the tilt of the iSpindel        
>Enter the measured points in the Excel sheet (see below). This Excel sheet will calculate the formula for the reference***

***
 
## Improved method using fast fermenting (II)

This method is more precise since it will take the affect of CO2 formed during fermenting into account.

It's recommended you connect the iSpindel with [Ubidots](https://ubidots.com/) for easy reading of the measured tilts. Furthermore it is wise to change settings of the iSpindel so it sends new readings every 20 seconds. With such a short interval the measurements can be easily followed on the [Ubidots](https://ubidots.com/) website.

1. Put the iSpindel in clean (tap) water (0 º Plato or SG 1.000)      
>***Write down the measured tilt of the iSpindel***

2. Make a solution of sugar in water with the highest anticipated density. If you are brewing strong beers with a high starting density you should have reference measurements in this high range. For most brewers a solution with a density around 1.085 or around 20 degrees Plato will do.     
>*Example: 800 ml of water + 200 g crystal sugar.*

3. Add yeast to the sugar solution and let the iSpindel float in the solution         
>***Measure the density or the degrees Plato and write it down with the tilt of the iSpindel***

4. Measure the density of the fluid and the corresponding tilt of the iSpindle at regular intervals till the end of fermentation has been reached.      
>***Enter the measured values in the Excel sheet. This sheet will show the formula of the calibration curve.***     
>
>****Caution: if you measure in Brix value with a refractometer you have to recalculate the measured value to correct for the alcohol reading*** 

***

# Formula

- ## [Online Gravity Calibration tool](http://www.ispindel.de/tools/calibration/calibration.htm)

The measured values can be entered in the field SG/Plato or BRIX plus the corresponding Tilt. It will calculate a formula of 2nd or 3rd degree that will predict the density or the degrees of Plato given an tilt value. This formula has to be entered in Firmware to be able to get readings in density or degrees Plato.

***

- ## Excel Sheet

The measured values can be entered in the Excel sheet. This sheet will calculate a formula that will predict the density or the degrees of Plato given an tilt value. This formula has to be entered in Firmware to be able to get readings in density or degrees Plato.
Other readings, such as apparent attenuation or alcohol % can be obtained in similar manners with the use of a 'Derived Variable' in [Ubidots](https://ubidots.com/).

1. First enter the measured values in Excel:    
[Download Excel table](https://github.com/universam1/iSpindel/blob/master/docs/Kalibrierung_en.xlsm)
2. Start the macro **Formule update** by clicking on the button. The formula will be updated.     
![Excelcalc](/pics/Excelcalc.jpg)
3. In the account of [Ubidots](https://ubidots.com/) a **Derived Variable** has to be added. This is a variable that is calculated with other variables as source. This can be done by following the next steps.
4. In [Ubidots](https://ubidots.com/) go to **Source**
5. Choose iSpindel as source
6. Click on **(+) Add variable** 
7. Choose **Derived**      
![Derived](/pics/Ubiderived.jpg)
8. Now you can fill in the formula from Excel. De parts in the formula shown as ***(tilt)*** has to be replaced. To do so click on ***insert variable*** and choose **tilt**. Give the newly created variable a name that does make sense, i.e. Density or Plato     
![Ubiplato](/pics/Ubiplato.jpg)
9. Under **Dashboard** you can create graphical presentations of your data.
