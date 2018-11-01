## Webcam_circles
Circle detection from online webcam images

## Transformada de Hough

Aquesta eina de processament de la imagte permet reconèixer figures que tenen una representació matemàtica; alguns exemples podrien ser circumferències, línies rectes o rectangles.

A partir de la imatge es poden trobar punts que es detectin com a vores d'un objecte; a partir d'aquesta primera detecció, s'ha de poder definir la quantitat de punts que formen part d'una forma geomètrica. Només analitzant el punts trobats, podríem tenir múltiples solucions de la forma geòmetrica que podem trobar (per exemple en el cas de les rectes).

Per tal d'evitar aquests errors, la transformada de Hough analitza les dades des d'un punt de vista paramètric (amb dos paràmetres, r i O), amb els quals obtindrem curves per a cada punt considerat com a vora d'un objecte. Per a cada curva que s'obté, es representa en un mapa
, i es van acumulant aquestes curves. Al final s'obté un mapa amb totes les curves;Els pics resultants del mapa a partir de l'acumulació ens permetràn determinar el tipus de forma geomètrica de la imatge. 
a
A partir de la modificació del rang dinàmic i  del contrast de la imatge, es poden observar zones o patrons d'informació que permeten evaluar, per exemple, la quantitat de segments que es troben en una figura. 

Un cop es detecta la figura i la quantitat de segments, es treu la imformació del mapa de Hough i es torna a recomposar. Al recomposar-ho, obtindrem la figura geomètrica.


## Canvis de paràmetres

A continuació s'explicaran els paràmetres definits el seu efecte en la imatge resultant:

*GAUSSIAN_BLUR_SIZE* - Amb aquest paràmetre definim l'amplada de la matriu Gaussiana que serveix posteriorment per a la reducció del soroll de la imatge (smoothing). Al baixar el seu valor, observem que el sistema és més sensible al soroll, la qual cosa provoca la detecció de cercles inexistents.

*GAUSSIAN_BLUR_SIGMA*

*HOUGH_ACCUM_RESOLUTION* - determina la resolució del acumulador.

*MIN_CIRCLE_DIST* - Especifica la distància mínima entre cercles a detectar. Ha de tenir un valor mitjà, degut a que un número molt gran pot prescindir de la detecció d'alguns cercles, mentre que un nombre petit podria ajuntar dos cercles en un.

*CANNY_EDGE_TH* - Determina el treshold per un operador anomenat *Canny*, que permet la detecció de vores. Veiem que el valor és molt alt al principi; si el baixem per complet, observem que es detecten a la imatge múltiples cercles inexistents. Això és degut a que al baixar el valor del treshold de manera abrupta, apareguin inherentment fragments de vores a la sortida que poden donar a equivocació en la detecció de vores.

*HOUGH_ACCUM_TH* - 

*MIN_RADIUS* - Indica el radi mínim del cercle a detectar. Aquest valor anirà definit segons les necessitats de l'aplicació.

*MAX_RADIUS* - Indica el radi màxim del cercle a detectar. Aquest valor anirà definit segons les necessitats de l'aplicació.

## Referències

Hough Transform *http://homepages.inf.ed.ac.uk/rbf/HIPR2/hough.htm*

Canny Edge Detector *http://homepages.inf.ed.ac.uk/rbf/HIPR2/canny.htm*

Smoothing Images *https://docs.opencv.org/3.3.1/dc/dd3/tutorial_gausian_median_blur_bilateral_filter.html*

OpenCV Hough Circle Transform *https://docs.opencv.org/3.4/d3/de5/tutorial_js_houghcircles.html*
