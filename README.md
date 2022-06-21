# IA: Detector de Cansancio con MediaPipe y OpenCV
A lo largo de este proyecto se utilizará Mediapipe para estimar puntos de referencia tanto faciales como corporales, obtenidos directamente de una WebCam a través de la OpenCV . Con esos datos, se crearán modelos personalizados de clasificación de poses que le permitan decodificar lo que una persona podría estar diciendo con su lenguaje corporal con gran precisión, adaptando a las necesidades de cada aplicación. En este proyecto en concreto, se tratará de realizar detección de somnolencia para conductores.

**MediaPipe:** ofrece soluciones de ML como el reconocimiento facial, mallas faciales, holístico, poses, detección de objetos, Motion Tracking etc. Para nuestra propuesta, utilizaremos el holístico, lo que nos permitirá reconocer en vivo de la pose humana simultánea , los puntos de referencia faciales y el seguimiento de mano. Obtendremos puntos coordenadas numéricas de articulaciones los cuales guardaremos en un .csv para su posterior tratamiento. Se puede apreciar mejor en este .gif obtenido de https://google.github.io/mediapipe/solutions/holistic.html.
 
<div style="width: 100%; clear: both;">
<div style="float: center; width: 100%;">
<img src="https://google.github.io/mediapipe/images/mobile/holistic_sports_and_gestures_example.gif", align="center">
 
 
Todos los landmarks del pose que detecta MediaPipe (33) se recogen en la siguiente imagen:
 
<div style="width: 100%; clear: both;">
<div style="float: center; width: 100%;">
<img src="https://google.github.io/mediapipe/images/mobile/pose_tracking_full_body_landmarks.png", align="center">

 ---
 
 
Utilizaremos estos landmarks, junto a las faciales, para tratar de predecir con distintos algoritmos de Machine Learning el cansancio. Cuando la probabilidad de que el/la conductor/a es mayor que 70%, lanzaremos una alerta para que pare a descansar.
 
 ---
 Todo el código está explicado en el notebook DETECTOR CANSADO-DESPIERTO CON IA.ipynb. 
 ---
 
Los resultados obtenidos han sido satisfactorios (se muestran en el siguiente .gif) y podrían mejorarse teniendo más datos entrenados o tomando en cuenta más variables en cuanto al cansancio. Incluso se podría estudiar más clases donde añadiríamos distintos grados de cansancio.

 <div style="width: 100%; clear: both;">
<div style="float: center; width: 100%;">
<img src="https://i.ibb.co/pfYBY9H/Cansadodespierto.gif", align="center">
