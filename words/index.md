<div class="section">
    <div>
    	<iframe id="splash" width="960" height="480" src="banners/splash.html"></iframe>
        <div style="top: 70px;font-size: 75px;font-weight: bold;">
        	¿Qué pasará ahora?
       	</div>
		<div style="font-weight: 500;top: 140px;left: 10px;font-size: 29px;">
			Posibles escenarios futuros de la COVID-19 explicados con simulaciones
		</div>
		<div style="font-weight: 100;top: 189px;left: 10px;font-size: 19px;line-height: 21px;">
			<b>
				🕐 30 min lectura
				&nbsp;&middot;&nbsp;
			</b>
			por
			<a href="https://scholar.google.com/citations?user=_wHMGkUAAAAJ&amp;hl=en">Marcel Salathé</a>
			(epidemiólogo)
			&
			<a href="https://ncase.me/">Nicky Case</a>
			(arte/código)
		</div>
	</div>
</div>

Lo de «sólo tenemos que temer al propio miedo» no es tan buen consejo.

Por supuesto, no hay que hacer acopio de papel higiénico, pero si los funcionarios públicos tienen miedo al miedo solamente tenderán a minimizar los peligros reales para evitar la «histeria colectiva». El problema no es el miedo, sino el cómo *canalizamos* nuestro miedo. El miedo nos permite prepararnos y fortalecernos para enfrentar los peligros actuales y futuros.

Sinceramente, estamos preocupados. ¡Y pensamos que seguramente tú también lo estás! Por eso, canalizamos nuestro miedo en la construcción de estas simulaciones, y te recomendamos que tu canalices el tuyo en aprovecharlas y lo conviertas en conocimiento. 


* **Los últimos meses** (introducción a la epidemiología, modelo SEIR, R y R<sub>0</sub>).
* **Los próximos meses** (confinamientos, rastreo de contactos, mascarillas).
* **Los próximos años** (¿pérdida de inmunidad? ¿ausencia de vacunas?).

El objetivo de esta guía es darte esperanza *y* tal vez, por qué no... miedo. Para vencer a la COVID-19 **de una forma que también proteja nuestra salud mental y financiera**, necesitamos optimismo para crear planes a futuro y pesimismo para crear planes de contingencia. Como dijo la escritora inglesa Gladys Bronwyn Stern *«El optimista inventa el avión y el pesimista, el paracaídas».*

[^timestamp]: Estas notas al pie de página mostrarán fuentes, enlaces y comentarios extra. ¡Como este comentario!
    
Si bien es cierto que muchos de los detalles de este contenido caducarán eventualmente, estamos seguros de que cubre el 95% de los posibles escenarios futuros, y que los conceptos básicos de epidemiología te serán útiles a partir de ahora.

Abróchate el cinturón: vamos a sufrir turbulencias.

<div class="section chapter">
    <div>
		<img src="banners/curve.png" height=480 style="position: absolute;"/>
        <div>Los últimos meses</div>
    </div>
</div>

Los pilotos usan simuladores de vuelo para aprender a evitar estrellar aviones.

**Los epidemiólogos usan simuladores de epidemias para aprender a evitar que se estrelle la humanidad.**

Así que, ¡hagamos un «simulador de vuelo de epidemias» muy, *muy* simple! En esta simulación, las <icon i></icon> personas Infecciosas pueden convertir a las <icon s></icon> personas Susceptibles en aún más <icon i></icon> personas Infecciosas:

![](pics/es_ES/spread.png)

Se estima que, *al comienzo* de un brote de la COVID-19, el virus salta de una <icon i></icon> a una <icon s></icon> cada 4 días, *en promedio*.<!--[^serial_interval]--> (Recuerda que hay mucha variabilidad).

[^serial_interval]: «The mean [serial] interval was 3.96 days (95% CI 3.53–4.39 days)». [Du Z, Xu X, Wu Y, Wang L, Cowling BJ, Ancel Meyers L](https://wwwnc.cdc.gov/eid/article/26/6/20-0357_article) (Aviso: La publicación temprana de estos artículos no están consideradas como versiones finales)

Si simulamos que se «duplique cada 4 días» *y nada más*, en una población que al comienzo sólo tiene 0.001% <icon i></icon>, ¿qué pasa?


[^caveats]: **   **

*Recuerda: todas estas simulaciones están muy simplificadas por motivos didácticos.*
    
Cuando le decimos a la simulación «infecta a 1 persona cada X días», en realidad se está incrementando el número de infectados en una relación de 1/X cada día,  es decir,  si simulamos 10 días la relación seria 1/10 o 0.10. Lo mismo para simulaciones futuras de recuperados cada X días, en realidad se reduce el número de infectados en una relación de 1/X por día.
    
En realidad, estas relaciones *no son* exactamente lo mismo, pero se aproximan lo suficiente para propósitos didácticos, y es más claro que ajustar las tasas de transmisión y recuperación directamente.

**¡Haga clic al botón «Iniciar» para comenzar la simulación! Podrás reiniciarla luego con diferentes ajustes:** 

<div class="sim">
	<iframe src="sim?stage=epi-1" width="800" height="540"></iframe>
</div>

Esta es la **curva de crecimiento exponencial.** Comienza con una cantidad muy baja y en determinado momento explota y pasa de ser un «ah, solo una gripe» a un «ah, la gripe no crea *fosas comunes en ciudades desarrolladas*».

![](pics/es_ES/exponential.png)

Pero esta simulación no es correcta. El crecimiento exponencial, afortunadamente, no puede continuar indefinidamente. Una cosa que detiene el contagio es cuando *ya hay* personas que tienen el virus:

![](pics/es_ES/susceptibles.png)

Cuantas más <icon i></icon>s haya, más rápido las <icon s></icon>s se vuelven <icon i></icon>s, **pero cuantas menos <icon s></icon>s haya, más *lento* la <icon s></icon>s se convertirán en <icon i></icon>s.**

¿Cómo cambia esto el crecimiento de la epidemia? Vamos a comprobarlo:

<div class="sim">
	<iframe src="sim?stage=epi-2" width="800" height="540"></iframe>
</div>

Esta es la **curva de crecimiento logística** con forma de S. Comienza muy pequeña, luego explota y luego se desacelera.

Pero. Esta simulación *todavía* no es correcta. No estamos teniendo en cuenta que las personas <icon i></icon> Infecciosas dejan de serlo en determinado momento, ya sea porque 1) se recuperan, 2) se «recuperan» con daños pulmonares, o 3) se mueren.

Para simplificar la cuestión, vamos a asumir que todas las personas <icon i></icon> Infecciosas pasan a <icon r></icon> Recuperadas. (Pero recuerda que en realidad algunas fallecen). Las <icon r></icon>s no pueden infectarse de nuevo, y vamos a asumir –*¡por ahora!*– que serán inmunes el resto de sus vidas.

Con la COVID-19, se estima que eres <icon i></icon> Infeccioso durante 10 días, *en promedio*.<!--[^infectiousness]--> Eso significa que algunas personas se recuperan antes de 10 días y otras después. **Aquí se ve cómo es eso, con una simulación que *comienza* con un 100% de <icon i></icon>:**

[^infectiousness]: «The median communicable period \[...\] was 9.5 days». [Hu, Z., Song, C., Xu, C. et al](https://link.springer.com/article/10.1007/s11427-020-1661-4) Sí, sabemos que la «mediana» no es lo mismo que la «media». Pero para propósitos educativos, se parecen bastante.

<div class="sim">
	<iframe src="sim?stage=epi-3" width="800" height="540"></iframe>
</div>

Esto es lo contrario de un crecimiento exponencial, la **curva de decaimiento exponencial.**

Y ahora, ¿qué pasa si simulas un crecimiento logístico con forma de S *con* recuperación?

![](pics/es_ES/graphs_q.png)

Vamos a comprobarlo.

La <b style='color:#ff4040'>curva roja</b> son los casos *actuales* <icon i></icon>,    
La <b style='color:#999999'>curva gris</b> son los casos *totales* (actuales + recuperados <icon r></icon>),
comienzan con solo 0.001% <icon i></icon>:

<div class="sim">
	<iframe src="sim?stage=epi-4" width="800" height="540"></iframe>
</div>

¡Y *de ahí* es de donde viene la famosa curva! No es una curva de Bell, ni siquiera una curva «log-normal». No tiene nombre. Pero la habrás visto un millón de veces esperando y deseando se aplane.

Éste es el **modelo SIR**,<!--[^sir]-->    
(<icon s></icon>**S**usceptibles <icon i></icon>**I**nfecciosos <icon r></icon>**R**ecuperados)      
la *segunda* idea más importante de conceptos básicos de Epidemiología es:

[^sir]: Para más detalles técnicos del modelo SIR, consultar [Institute for Disease Modeling](https://www.idmod.org/docs/hiv/model-sir.html#) y [Wikipedia](https://es.wikipedia.org/wiki/Modelo_SIR)

![](pics/es_ES/sir.png)

**NOTA: ¡Las simulaciones usadas en la toma de decisiones públicas son mucho, *mucho* más sofisticadas que ésta!** Pero el modelo SIR puede explicar los mismos fenómenos generales, aún sin todos sus matices.

Bueno, vamos a añadir otro matiz más: antes de que <icon s></icon> se convierta en <icon i></icon>, deben convertirse en personas <icon e></icon> Expuestas. Esto pasa cuando tienen el virus, pero aún no pueden transmitirlo –*infectadas*, pero todavía no son *infecciosas*.

![](pics/es_ES/seir.png)

(Esta variante es el denominado **modelo SEIR**<!--[^seir]-->, donde «E» son las <icon e></icon> personas «Expuestas». Ten en cuenta que este *no es* el significado habitual de «expuesto», cuando podrías tener o no el virus. En esta definición técnica, «Expuesto» significa que lo tienes con seguridad. La terminología científica no ayuda mucho a la comprensión).

[^seir]: Para más explicaciones técnicas del modelo SEIR, consultar [Institute for Disease Modeling](https://www.idmod.org/docs/hiv/model-seir.html) and [Wikipedia](https://es.wikipedia.org/wiki/Modelaje_matemático_de_epidemias#Modelo_SEIR)

Para la COVID-19, se estima que las personas son <icon e></icon> infectadas, pero aún no infecciosas (expuestas) durante 3 días *en promedio*.<!--[^latent]--> ¿Qué pasa si añadimos eso a la simulación?

[^latent]: «Assuming an incubation period distribution of mean 5.2 days from a separate study of early COVID-19 cases, we inferred that infectiousness started from 2.3 days (95% CI, 0.8–3.0 days) before symptom onset». (Traducción: Si asumimos que los síntomas comienzan a los 5 días, la fase infecciosa comienza 2 días antes = la contagiosidad comienza a los 3 días) [He, X., Lau, E.H.Y., Wu, P. et al.](https://www.nature.com/articles/s41591-020-0869-5)

La <b style='color:#ff4040'>curva roja <b style='color:#FF9393'>+ rosa</b></b> son casos *actuales* (infecciosos <icon i></icon> + expuestos <icon e></icon>),    
La <b style='color:#888'>curva gris</b> son casos *totales* (actuales + recuperados <icon r></icon>):

<div class="sim">
	<iframe src="sim?stage=epi-5" width="800" height="540"></iframe>
</div>

¡Sin grandes cambios! El tiempo en el que se está <icon e></icon> Expuesto cambia en proporción de <icon e></icon>-a-<icon i></icon>, y de cuando ocurre su pico de casos actuales... pero la *altura* de ese pico y el total de casos al final no cambia.

¿Por qué? Por el *primero* y más importante concepto básico de la Epidemiología:

![](pics/es_ES/r.png)

Abreviación de «número reproductivo». Es el número de personas *promedio* a las que una <icon i></icon> contagia *antes* de recuperarse (o fallecer).

![](pics/es_ES/r2.png)

**R** cambia durante el transcurso de un brote, según se obtiene más inmunidad y se realizan más intervenciones.

**R<sub>0</sub>** es el número R *al comienzo de un brote, antes de la inmunidad o las intervenciones*. R<sub>0</sub> refleja sobre todo el poder del propio virus, aunque cambia de un lugar a otro. Por ejemplo, R<sub>0</sub> es mayor en ciudades de gran densidad que en las áreas rurales y dispersas.

(La mayoría de los artículos periodísticos –¡incluso algunos artículos científicos!– confunden R y R<sub>0</sub>. De nuevo, la terminología científica no ayuda a la comprensión).

El R<sub>0</sub> para «la» gripe estacional es de 1.28<!--[^r0_flu]-->. Esto implica que, al *comienzo* de un brote, cada <icon i></icon> contagia a otras 1.28 personas *en promedio.* (Si le parece extraño que no sea un número entero recuerde que una madre «promedio» tiene 2.4 hijos. Lo que no significa que tengan a medio bebé gateando a su alrededor).

[^r0_flu]: «The median R value for seasonal influenza was 1.28 (IQR: 1.19–1.37)» [Biggerstaff, M., Cauchemez, S., Reed, C. et al.](https://bmcinfectdis.biomedcentral.com/articles/10.1186/1471-2334-14-480)

El R<sub>0</sub> para la COVID-19 se estima en 2.2,<!--*[^r0_covid]--> aunque un estudio *aún-no-finalizado* lo estima en 5.7<!--(!)--> en Wuhan.<!--[^r0_wuhan]-->

[^r0_covid]: «We estimated the basic reproduction number R0 of 2019-nCoV to be around 2.2 (90% high density interval: 1.4–3.8)» [Riou J, Althaus CL.](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7001239/)

[^r0_wuhan]: «we calculated a median R0 value of 5.7 (95% CI 3.8<!--.9)-->[Sanche S,<!--in YT, Xu C-->Romero-Severson E, Hengartner N, Ke R.](https://wwwnc.cdc.gov/eid/article/26/7/20-0282_article)

En nuestras simulaciones –*al inicio y en promedio*– una <icon i></icon> infecta a alguien cada 4 días, durante 10 días. «10 días» equivale a «4 días» dos veces y medio. Esto significa que –*al inicio y en promedio*– cada <icon i></icon> contagia a otras 2.5 personas. Por tanto, R<sub>0</sub> = 2.5. <!--(matizaciones:[^r0_caveats_sim])-->

[^r0_caveats_sim]: Esto asume que una persona es igual de contagiosa durante todo el periodo infeccioso. De nuevo, es una simplificación en aras de la didáctica.

**Juegue con esta calculadora de R<sub>0</sub>, para ver como R<sub>0</sub> depende del tiempo de recuperación y del tiempo de un nuevo contagio:**

<div class="sim">
	<iframe src="sim?stage=epi-6a&format=calc" width="285" height="255"></iframe>
</div>

Pero recuerde, cuantas menos personas <icon s></icon>s haya, más *lentamente* se convertirán las <icon s></icon>s en <icon i></icon>s. El número de reproducción *actual* (R) depende no sólo del número de reproducción *básico* (R<sub>0</sub>), sino *también* de cuantas personas dejan de ser <icon s></icon> Susceptibles. (Por ejemplo, debido a la recuperación y obteniendo inmunidad natural).

<div class="sim">
	<iframe src="sim?stage=epi-6b&format=calc" width="285" height="390"></iframe>
</div>

Cuando haya un número suficiente de personas con inmunidad, R < 1, y el virus esté contenido, eso se llama **inmunidad de grupo**. Para la gripe la inmunidad de grupo se consigue *con una vacuna*. Intentar alcanzar la «inmunidad de grupo natural» dejando que las personas se contagien es una idea *terrible*. (¡Pero no por la razón que quizá estás pensando! más adelante lo explicaremos).

Ahora, juguemos con el modelo SEIR otra vez, pero mostrando R<sub>0</sub>, R en el tiempo y el umbral de la inmunidad de grupo:

<div class="sim">
	<iframe src="sim?stage=epi-7" width="800" height="540"></iframe>
</div>

**NOTA: ¡Los casos totales *no se detienen* al llegar a la inmunidad de grupo, sino que lo exceden!** Y cruza el umbral *exactamente* cuando se llega al pico de casos actuales. (Eso ocurre cualesquiera que sean los ajustes –¡inténtalo tú mismo!)

Esto pasa porque cuando hay más no-<icon s></icon>s que el umbral de inmunidad de grupo, tenemos R < 1. Y cuando R < 1, el número de nuevos casos deja de crecer: un pico.

**Si sólo hubiera una lección que pudieras llevarte sería ésta ** –es un diagrama extremadamente complejo así que, por favor, tómate tu tiempo para comprenderlo en su totalidad:

![](pics/es_ES/r3.png)

**Esto significa: ¡NO necesitamos detener todos los contagios, o casi todos los contagios, para detener a el COVID-19!**

Es una paradoja. El COVID-19 es extremadamente contagioso, pero para contenerlo, «sólo» necesitamos evitar al menos el 60% de las infecciones. ¿¡El 60%!? Si fuera una nota de la escuela, sería un 6. Pero si R<sub>0</sub> = 2.5, disminuir eso un 61% nos da R = 0.975, que es R < 1, ¡el virus está contenido!<!--(Fórmula exacta:[^exact_formula])-->

<!--[^exact_formula]: Recuerda R = R<sub>0</sub> * la tasa de contagios aún permitidos. Recuerda también que la tasa de contagios permitidos = 1 - tasa de contagios *evitados*.
    
Por tanto, para llegar a R < 1, tienes que conseguir que R<sub>0</sub> * ContagiosPermitidos < 1. 
    
Por tanto, ContagiosPermitidos < 1/R<sub>0</sub>
    
Por tanto, 1 - ContagiosEvitados < 1/R<sub>0</sub>
    
Por tanto, ContagiosEvitados > 1 - 1/R<sub>0</sub>
    
Por tanto, ¡debes evitar más de **1 - 1/R<sub>0</sub>** de los contagios para que R < 1 y así contener el virus! -->

![](pics/es_ES/r4.png)

(Si consideras que R<sub>0</sub> o el resto de números de nuestras simulaciones son muy pequeños/grandes, ¡bienvenidos los cuestionamientos! Habrá un simulador al final de esta guía, donde podrás indicar tus *propios* números y simular lo que ocurre con ellos).

*Todas* las medidas de prevención y reacción para la COVID-19 que has oído –lavado de manos, distanciamiento social/físico, confinamientos, auto-aislamiento, cuarentenas y rastreo de contactos, mascarillas, incluso la «inmunidad de grupo»– *todas* hacen exactamente lo mismo:

Hacer que R < 1.

Así que ahora vamos a usar nuestro «simulador» para averiguar lo siguiente: ¿Cómo hacemos que R < 1 de forma que **también proteja nuestra salud mental *y* financiera?**
