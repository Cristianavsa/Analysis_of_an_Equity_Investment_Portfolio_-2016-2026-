<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <title>Análisis y simulación de un portafolio de inversión en acciones</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        body {
            font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
            margin: 0;
            padding: 2rem;
            line-height: 1.6;
            background-color: #f5f5f5;
            color: #222;
        }
        main {
            max-width: 900px;
            margin: 0 auto;
            background: #ffffff;
            padding: 2rem;
            border-radius: 8px;
            box-shadow: 0 4px 12px rgba(0,0,0,0.06);
        }
        h1, h2 {
            color: #1f2933;
        }
        h1 {
            margin-top: 0;
            border-bottom: 2px solid #e5e7eb;
            padding-bottom: 0.5rem;
        }
        h2 {
            margin-top: 2rem;
        }
        p {
            margin-bottom: 1rem;
        }
        strong {
            font-weight: 600;
        }
    </style>
</head>
<body>
<main>
<h1>Análisis y simulación de un portafolio de inversión en acciones</h1>

<h2>Contexto</h2>
    <p>
        Para iniciar el análisis se definieron los tickers de las acciones seleccionadas y el benchmark de referencia.
        El portafolio está compuesto por cuatro empresas de gran capitalización —Apple (AAPL), Microsoft (MSFT),
        Amazon (AMZN) y JPMorgan Chase (JPM)— mientras que el Vanguard S&amp;P 500 ETF (VOO) se utiliza como índice
        comparativo debido a su amplia diversificación y representatividad del mercado estadounidense.
    </p>
    <p>
        Con el objetivo de realizar un estudio histórico robusto, se estableció un rango temporal de diez años,
        desde el 1 de enero de 2016 hasta el 1 de enero de 2026, lo que permite capturar distintos ciclos de mercado,
        periodos de volatilidad y eventos relevantes que pudieron afectar el comportamiento de los activos.
    </p>
    <p>
        Posteriormente, se construyó una ruta para almacenar los datos descargados en la carpeta <strong>data/raw</strong>,
        asegurando una estructura organizada para el manejo de información. Para obtener los precios históricos,
        se implementó la función <strong>download_prices()</strong>, la cual utiliza la librería <strong>yfinance</strong>
        para descargar automáticamente los precios diarios de cada ticker en formato largo (<em>long format</em>).
        Esta estructura facilita el procesamiento posterior, como el cálculo de retornos, drawdowns, correlaciones
        y métricas de riesgo.
    </p>
    <p>
        Este conjunto de datos constituye la base para el análisis cuantitativo del portafolio y permite evaluar
        su desempeño frente al benchmark seleccionado.
    </p>

<h2>Objetivo</h2>
    <p>
        Responder: <strong>“¿Cómo habría evolucionado el portafolio de un cliente en los últimos 10 años
        y qué ajustes recomendaría hoy?”</strong>
    </p>

<h2>Análisis</h2>
    <p>
        Durante el periodo analizado, el portafolio compuesto por Apple (AAPL), Microsoft (MSFT), Amazon (AMZN)
        y JPMorgan Chase (JPM) muestra patrones de comportamiento que se asemejan considerablemente al benchmark
        seleccionado, el fondo indexado Vanguard S&amp;P 500 ETF (VOO). Esta similitud es esperada, ya que varias
        de las acciones del portafolio también forman parte del índice, lo que naturalmente alinea su evolución
        con la del mercado en general.
    </p>
    <p>
        Tras descargar y procesar los datos históricos desde el 1 de enero de 2016 hasta el 1 de enero de 2026,
        se calcularon los retornos diarios para evaluar las características de riesgo y rendimiento del portafolio.
        Posteriormente, se aplicaron pruebas estadísticas con el fin de determinar si el portafolio presenta un
        comportamiento significativamente diferente al del benchmark.
    </p>
    <p>
        La prueba t de diferencia de medias indica que los rendimientos promedio del portafolio no son
        estadísticamente distintos de los del VOO. Esto sugiere que, aunque existen fluctuaciones a corto plazo,
        el portafolio no genera rendimientos extraordinarios ni significativamente superiores en comparación con
        el índice. En otras palabras, su desempeño a largo plazo se mantiene alineado con el mercado.
    </p>
    <p>
        De manera similar, la prueba de Levene para igualdad de varianzas no muestra evidencia sólida de diferencias
        en la volatilidad entre el portafolio y el benchmark. Este resultado refuerza la conclusión de que el
        portafolio se comporta de manera consistente con el mercado tanto en términos de riesgo como de retorno.
    </p>
    <p>
        En conjunto, el análisis revela que el portafolio ha evolucionado de forma estable y predecible durante los
        últimos años, siguiendo de cerca los movimientos del benchmark. Si bien esto refleja una alineación sólida
        con el desempeño del mercado, también indica una limitada diferenciación. Las recomendaciones de ajuste
        dependerán del perfil de riesgo del cliente, sus objetivos de diversificación y su interés en buscar
        rendimientos superiores mediante una asignación estratégica o exposición a clases de activos alternativas.
    </p>

<h2>Hallazgos</h2>
    <p>
        El análisis del comportamiento histórico de las acciones seleccionadas revela una tendencia claramente
        alcista en sus rendimientos acumulados durante el período evaluado. Entre los activos analizados, Apple
        destaca como el de mayor crecimiento, superando el 1000% de rendimiento acumulado, seguido por Microsoft,
        con un crecimiento cercano al 900%, ambos muy por encima del benchmark VOO, cuyo rendimiento acumulado fue
        aproximadamente del 300%.
    </p>
    <p>
        El portafolio, compuesto por Apple, Microsoft, Amazon y JPMorgan Chase, también mostró un desempeño sólido,
        alcanzando un rendimiento acumulado cercano al 744%, más del doble del rendimiento del benchmark. Sin embargo,
        es importante señalar que el portafolio no supera individualmente a las acciones de Apple y Microsoft, que
        presentan crecimientos extraordinarios.
    </p>
    <p>
        En términos de riesgo, Amazon se posiciona como el activo más volátil, con una volatilidad superior al 32%,
        seguida de Apple con aproximadamente 29%. El benchmark VOO exhibe un riesgo considerablemente menor, con una
        volatilidad cercana al 18%, reflejando un comportamiento más estable. El portafolio, con una volatilidad de
        21.99%, se ubica como el segundo activo menos riesgoso del conjunto.
    </p>
    <p>
        Respecto al rendimiento ajustado por riesgo, Apple y Microsoft son los activos más eficientes, generando
        alrededor de 0.90 unidades de retorno adicional por unidad de riesgo. El benchmark también muestra una buena
        eficiencia, con aproximadamente 0.70 unidades de retorno por unidad de riesgo. El portafolio presenta una
        eficiencia destacada, entregando casi una unidad completa de retorno adicional sobre la tasa libre de riesgo
        de manera anualizada.
    </p>
    <p>
        En cuanto al riesgo de pérdida, el portafolio registra el menor drawdown del conjunto, con una caída máxima
        de −29.74%, mejor que el benchmark (−33.99%). Amazon, por su parte, experimentó una caída máxima casi del
        doble que la del portafolio, evidenciando una mayor exposición al riesgo extremo.
    </p>
    <p>
        Finalmente, la correlación entre los activos es elevada, especialmente entre el portafolio y el benchmark
        (0.94), debido a que varios activos del portafolio también forman parte del índice. Las pruebas estadísticas
        realizadas indican que no existe evidencia sólida de que el portafolio genere rendimientos significativamente
        superiores al benchmark, lo que sugiere que ambos se comportan de manera similar en términos de retornos
        promedio.
    </p>

<h2>Conclusiones</h2>
    <p>
        El portafolio analizado ha mostrado un desempeño sólido y una tendencia alcista durante el período evaluado,
        superando ampliamente el rendimiento acumulado del benchmark VOO. Sin embargo, este desempeño está
        fuertemente influenciado por el extraordinario crecimiento de Apple y Microsoft, cuyos rendimientos
        individuales superan incluso al portafolio en su conjunto.
    </p>
    <p>
        A pesar de su buen rendimiento, el portafolio no presenta diferencias estadísticamente significativas respecto
        al benchmark en términos de retornos promedio, lo que indica que su comportamiento general está alineado con
        el mercado. No obstante, el portafolio ofrece una mejor eficiencia riesgo‑retorno y un menor drawdown, lo que
        lo convierte en una alternativa atractiva desde una perspectiva de gestión del riesgo.
    </p>
    <p>
        La elevada correlación con el benchmark sugiere que el portafolio está fuertemente vinculado al comportamiento
        del mercado, lo cual es coherente con su composición. Para mejorar la diferenciación y potencialmente
        incrementar el rendimiento ajustado por riesgo, podrían considerarse ajustes estratégicos en la asignación
        de activos, dependiendo del perfil del cliente y sus objetivos de inversión.
    </p>
</main>
</body>
</html>
