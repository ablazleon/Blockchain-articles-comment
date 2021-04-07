# 1 Lectura del articulo que describe Bitcoin

# 2 Lectura del articulo que describe el ordenamiento temporal de eventos


----------

# Lectura del articulo que describe Bitcoin

Se ha de leer el articulo inicial que describe Bitcoin  ( https://bitcoin.org/bitcoin.pdf ).  Realizar un breve resumen de los incentivos para unirse desde la teoría de juegos así como el algoritmo de consenso. 

A continuación, tras leer el artículo inicial que describe bitcoin, resumo, primero, en general qué plantea el artículo, después, desde un punto de vista de teoría de juegos los incentivos para unirse. Finalmente, se describe el algoritmo de consenso., en relación a lo que se describe en este artículo, claro.

Primero, en general este artículo plantea en qué consiste el sistema de bitcoin. Bitcoin está pensado como un sistema "peer-to-peer de pago electrónico de efectivo". Con el fin de evitar un "ente intermedio de confianza", todas las transacciones se hacen publicas y los nodos pueden entonces verficarlas, sobre todo para evitar el "double spending", y así actuar como este "ente confiable". Para verificar cada transacción los nodos comprueban que cada transacción es válida, por ejemplo enviar 0.5 de A a B, comprobando que en efecto, A es A  a partir de su firma y luego comprobando que tiene esos fondos. Ahora bien, ¿quién puede escribir en el estado? ¿escribir una nueva transacción? Bitcoin plantea que una vez verficada la anterior transacción, que los nodos escriben nuevas transacciones y sólo las transacciones de los nodos que consiguen generar un cierto hash, son aceptadas por el resto de nodos, y por tanto la siguiente transacción se escribe sobre esta última transacción. 

Desde un punto de vista de teoría de juegos, el comportamiento de los agentes en el sistema de bitcoin, se puede considerar un juego cooperativo: existen distintos agentes que actúan según sus intereses. Los agentes/nodos pueden tomar decisiones: la decisión que se destaca es que si los agentes cooperan para aceptar ciertos hashes aunque no sean los establecidos válidos (cadena más corta, con el interés de aceptar ciertas transacciones, por ejemplo, quedarse con monedas) se pueden aceptar trasacciones que no estén, por tanto, "verificadas". En este contexto, se plantea un incentivo para que los agentes "se unan", un incentivo económico. Por un lado, los agentes quieren ser nodos para recibir una bonificación si se acepta su hash. El artículo realiza la compración de los mineros, que son compensados económicamente por poner oro en circulación. Por otro lado, debido a este incentivo económico, los agentes con más CPU, y por tanto, aquellos capaces de cambiar la cadena, se les bonifica si contribuyen a seguir "lo establecido" para que su valor económico no se vea devaluado.

Por otro lado, se discute el algoritmo de consenso de bitcoin, según descrito en este artículo. Se han identificado dos fases en este algoritmo de consenso, comparando con el algoritmo de Paxos. Primero se elige al líder, el nodo que es capaz de cambiar con su transacción el estado del sistema, cambio en el estado que luego se exporta al resto de nodos y queda registrado en el ledger. El método por el que se elige el nodo líder, es mediante prueba de trabajo, es decir el nodo que obtiene un hash con un cierto nonce antes y más largo. A continuación, estas transacciones son verificadas y con este hash, se exportan a los nodos, y si quedase aceptada, el cierto nodo creador de hash recibiría el incentivo económico. Esta segunda fase de exportación de la transacción, se podría identificar con la segunda fase en Paxos.

# 2. Lectura del articulo que describe el ordenamiento temporal de eventos

Leer el articulo de Leslie Lamport sobre el ordenamiento temporal de eventos.  Tal como se indicó en clase realizar un breve comentario sobre la convocatoria de elecciones en la comunidad de Madrid desde el punto de vista del ordenamiento temporal de eventos. ( https://lamport.azurewebsites.net/pubs/time-clocks.pdf ).

A continuación, se resume el artículo y se comenta brevemente la convocatoria de elecciones de la CAM (https://cadenaser.com/emisora/2021/03/10/radio_madrid/1615400702_552912.html)  desde un punto de vista de ordenamiento de eventos.

Este artículo de Lamport de 1978 (Time, Clocks and the Ordering of Events in a Distributed System) disecciona el concepto de "ordenamiento de eventos". A la tercera vez que lees el artículo descubres  se "meta" analiza este concepto, que en la primera lectura juzgas de intuitivo, con el fin de definir cómo implementar la sincronía en un sistema distribuido, "pilar" a "pilar". Es decir, que, por ejemplo, en un sistema en el que se ejecutan varios procesos P y Q, que Q tenga constancia de los mensajes que emite Q, q1, q2 y q3 y que emite P, p1, p2 y p3, y pueda establecer un cierto orden entre ellos. Para definir la estructura sobre la que abordar el "ordenamiento de eventos" el artículo, primero: introduce en qué consiste este problema sobre la incertidumbre de la ordenación de eventos en un sistema distribuido. Que sobre estos eventos sólo se puede extraer un ordenación parcial, y como objetivo se desea una ordenación total. A continuación, describe cómo, un proceso sí que puede juzgar un "Ordenamiento Parcial" de estos eventos. Después, se plantea qué es un "reloj lógico", básicamente un contador con timestamps para uniformizar 
esta ordenación parcial de eventos, permitiendo una "ordenación total de eventos". Si bien, esta ordenación parical, puede llevar a un comportamiento a nómalo en cuanto a que ese contador no ordena los eventos de forma general (o como dice el artíciulo, manteniendo una Condición de Reloj Fuerte). Finalmente, introduce que estableciendo unos tiemstamps genéricos, es decir, como relojes físicos, es la forma de garantizar ordenamiento sin estos compartamientos anómalos. 

Una vez se ha descrito como el artículo describe en qué conssite la Ordenación de Evetnos, se discute lo sucedido con la convocación de elecciones en la CAM

Si la orden es necesaria para que el estado actual sea consistente 

describe que se pueden ordenar eventos de forma total en base al ordenamiento lógico. En el caso de las elecciones de la CAM se produce un problema en cuanto al ordenamiento porque primero se anunció que se habían propuesto una moción de censura, pero antes se había propuesto la disolución del parlamento. 
