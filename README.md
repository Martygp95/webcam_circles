## webcam_circles
Circle detection from online webcam images

## Transformada de Hough

Aquesta eina de processament de la imagte permet reconèixer figures que tenen una representació matemàtica; alguns exemples podrien ser circumferències, línies rectes o rectangles.

A partir de la imatge es poden trobar punts que es detectin com a vores d'un objecte; a partir d'aquesta primera detecció, s'ha de poder definir la quantitat de punts que formen part d'una forma geomètrica. Només analitzant el punts trobats, podríem tenir múltiples solucions de la forma geòmetrica que podem trobar (per exemple en el cas de les rectes).

Per tal d'evitar aquests errors, la transformada de Hough analitza les dades des d'un punt de vista paramètric (amb dos paràmetres, r i O), amb els quals obtindrem curves per a cada punt considerat com a vora d'un objecte. Per a cada curva que s'obté, es representa en un mapa
, i es van acumulant aquestes curves. Al final s'obté un mapa amb totes les curves;Els pics resultants del mapa a partir de l'acumulació ens permetràn determinar el tipus de forma geomètrica de la imatge. 

A partir de la modificació del rang dinàmic i  del contrast de la imatge, es poden observar zones o patrons d'informació que permeten evaluar, per exemple, la quantitat de segments que es troben en una figura. 

Un cop es detecta la figura i la quantitat de segments, es treu la imformació del mapa de Hough i es torna a recomposar. Al recomposar-ho, obtindrem la figura geomètrica.

## Referències

Hough Transform *http://homepages.inf.ed.ac.uk/rbf/HIPR2/hough.htm*

