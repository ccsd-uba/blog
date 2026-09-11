+++
title = "Agentes, teoría de juegos y computadoras cuánticas: así fue el Web3 AI Summit en San Francisco"
description = "Diego Kingston, director de Investigación del CCSD, participó del Web3 AI Summit en San Francisco. Esta edición estuvo dominada por los agentes de IA, los pagos agénticos, la teoría de juegos aplicada a modelos y la transición post-cuántica."
date = 2026-09-11
[taxonomies]
tags = ["inteligencia artificial", "criptografía", "zk", "conferencias", "investigación"]
+++

![Diego Kingston en el campus de la Universidad de Stanford, durante su viaje al Web3 AI Summit](/images/web3-ai-summit-2026.jpg)

Este mes, Diego Kingston, director de Investigación de nuestro centro, participó del Web3 AI Summit en San Francisco, tal como en las tres ediciones anteriores, para conversar con investigadores y líderes de la industria sobre los últimos desarrollos en web3 y su intersección con la IA. Esta edición tomó un rumbo distinto al de años anteriores: mientras que antes el eje estaba puesto en identidad digital, tecnologías de privacidad y selective disclosure, esta vez la agenda estuvo dominada por los agentes de IA y por la transición post-cuántica. Era algo esperable, ya que la IA cambió la forma en que hacemos muchas cosas, incluida la programación y la búsqueda de información, y resulta natural que la industria empiece a explorar qué pasa cuando los agentes comienzan a transaccionar por sí mismos.

El evento se extendió a lo largo de dos días: el primero, dedicado en su mayoría a agentes de IA, y el segundo, a pruebas de conocimiento cero (zero-knowledge) y computación cuántica.

## Pagos agénticos

Varias empresas están trabajando en pagos agénticos, ya que estos podrían habilitar nuevos hábitos de consumo y ofrecer mejor experiencia de usuario y mejores precios, sin esfuerzo adicional de parte del usuario. El panorama general, bien descripto en el paper [Virtual Agent Economies](https://arxiv.org/pdf/2509.10147) de DeepMind, es uno en el que uno describe una intención simple (como planear un viaje o comprar algo) y el agente busca entre distintos proveedores, paga pequeños montos para acceder a mejores opciones y vuelve con una lista acotada para la aprobación final del usuario. Uno de los puntos que plantea el paper es que este tipo de economías deberían diseñarse de forma deliberada en lugar de dejar que emerjan por sí solas, y que decisiones como cuán permeable debería ser el límite entre la economía de agentes y la economía humana determinarán si el resultado es eficiente y justo, o extractivo.

Si bien crypto y x402 ofrecen una alternativa natural para manejar pagos agénticos, los proveedores de pago tradicionales también están participando en esta tecnología, llegando incluso a dar tarjetas de crédito a agentes. En uno de los análisis presentados en el summit, se estimó que el volumen de pagos agénticos genuinos en x402 se ubica entre el 0,6% y el 7,5% del volumen total, que al momento del estudio rondaba los 52 millones de dólares. Incluso tomando la cota superior, esto muestra que la infraestructura todavía va por delante de la demanda, aunque el volumen viene creciendo a un ritmo constante en los últimos meses y los agentes efectivamente ya están realizando pagos comerciales.

Para que todo esto sea viable a escala, hace falta un sistema de micropagos eficiente, ya que un agente que paga una fracción de centavo por consulta a varios proveedores antes de poder dar una respuesta terminará gastando en comisiones más de lo que vale la información. Por eso, la mayoría de los equipos con los que se conversó en el summit están construyendo payment channels, que permiten realizar varias microtransacciones off-chain, agregarlas y publicar un único settlement en la L2 o L1.

## Teoría de juegos cuando los jugadores son modelos

Otro de los temas centrales fue la teoría de juegos aplicada a agentes de IA. Varios grupos mostraron casos de uso y simulaciones usando el framework [Concordia](https://github.com/google-deepmind/concordia) de Google DeepMind, que permite construir mundos simulados poblados por agentes basados en LLMs. El trabajo reciente sobre [evaluación de capacidades de generalización de agentes basados en LLMs en escenarios de motivación mixta](https://arxiv.org/pdf/2512.03318) usa Concordia para poner agentes en juegos donde la cooperación y el interés propio están en tensión, y encuentra que los agentes que se comportan de forma cooperativa en situaciones conocidas no siempre generalizan ese comportamiento a situaciones nuevas. Esto es más que una curiosidad, ya que los agentes que se están desplegando hoy están empezando a negociar y transaccionar en nombre de los usuarios.

También hubo una discusión sobre si estos sistemas pueden exhibir comportamiento caótico, en línea con trabajos recientes sobre [paradojas de los equilibrios de teoría de juegos y el precio de la anarquía](https://arxiv.org/pdf/2607.11752), que sugieren que el equilibrio que uno diseña puede no ser el estado al que el sistema realmente converge cuando los participantes son algoritmos que aprenden. Por último, hubo discusiones sobre la "personalidad agéntica" (agentic personhood) y qué atributos debe exhibir un agente para calificar como tal, siguiendo el paper [A Pragmatic View of AI Personhood](https://arxiv.org/pdf/2510.26396), que plantea esa personalidad no como un umbral metafísico a cruzar, sino como un conjunto de derechos y responsabilidades que puede otorgarse de a partes, según lo que necesitemos que los agentes puedan hacer.

## ZK y el cronograma cuántico

El segundo día estuvo dedicado a la criptografía, con foco en el desarrollo y la mejora de sistemas de pruebas ZK usando IA y en los desafíos que todavía quedan por resolver. También hubo charlas sobre los últimos desarrollos en computadoras cuánticas basadas en átomos neutros, sus principios de funcionamiento y las mejoras en los requisitos para lograr una computadora cuántica criptográficamente relevante, que siguen bajando con cada nueva estimación. La sensación general es que el plazo se acerca más rápido de lo esperado, y una de las conclusiones (que también se había escuchado en Roma a principios de este año) es que, incluso si el cronograma termina siendo más largo, conviene actuar como si fuera corto, dado el nivel de incertidumbre.

Si bien algunas aplicaciones podrán actualizarse antes de que estas computadoras cuánticas estén disponibles, todavía hay partes importantes de internet y del hardware que dependen de criptografía de curvas elípticas, y migrar sistemas complejos a nuevas primitivas no es algo que pueda hacerse en pocos días. Además, las firmas que garantizan compromisos de varios años tienen que sobrevivir a la ventana de "harvest now, decrypt later", no solo resistir a los atacantes de hoy.

Por suerte, Ethereum ya se está moviendo en esta dirección y lidera el desarrollo de un esquema de firmas post-cuánticas agregables, útil para cualquier blockchain.

## Qué nos deja esto

Diego, que además de dirigir el área de Investigación del centro trabaja en Aligned, aprovechó el encuentro para conversar sobre algunas de las ideas y productos en los que viene trabajando ahí, pensando en este nuevo escenario, con agentes de IA haciendo comercio y la amenaza cuántica cada vez más cerca. Muchas de esas conversaciones volvían una y otra vez al mismo punto: la necesidad de verificar cómputo ajeno, de forma barata y con una seguridad que no caduque. En Aligned se sigue trabajando en el desarrollo de su zkVM (post-cuántica segura por diseño) y en agregación de pruebas, además de colaborar para tener protocolos eficientes de cara a esta próxima etapa.

Para quienes en el centro seguimos de cerca la intersección entre IA, criptografía y sistemas descentralizados, el summit deja un panorama claro de hacia dónde se mueve la industria. Fue una alegría reencontrarse con tantos colegas en San Francisco y ver cómo el ecosistema sigue evolucionando. Ahora, a seguir construyendo.
