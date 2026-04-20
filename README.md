<!doctype html>
<html lang="es">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>
  <body>
    <div>
      <!-- Canvas = etiqueta HTML5, que permite dibujar 2D, 3D -->
      <canvas id="lienzo"></canvas>
    </div>

    <!-- GRAFICO NO es estetico -->
    <!-- GRAFICO es un recurso de BI (Inteligencia de Negocios) -->
    <!-- GRAFICO representan resumenes -->
    <!-- GRAFICO debe ser simple de interpretar-->
    <!-- GRAFICO (libreria JS) <<<< JSON -->
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>

    <script>
      //Evento permite cargar las instrucciones cuando el DOM este listo
      document.addEventListener("DOMContentLoaded", function () {
        //Objeto para manipular el lienzo
        const lienzo = document.getElementById("lienzo");

        //Para recorrer un array utilizamos for, while, "FOREACH"
        //map() => devuelve un nuevo array, con la misma cantidad de elementos, pero con los valores transformados
        const data = [
            { grado: "Primero", tardanza: 15 },
            { grado: "Segundo", tardanza: 5 },
            { grado: "Tercero", tardanza: 15 },
            { grado: "Cuarto", tardanza: 20 },
            { grado: "Quinto", tardanza: 18 },
        ]

        //Construir Grafico => new Chart(lienzo, { configuraciones })
        const grafico = new Chart(lienzo, {
          type: "bar",
          data: {
            labels: data.map(fila => fila.grado),
            datasets: [
                {   
                    label: 'Turismo',
                    data: data.map(fila => fila.tardanza),
                    borderWidth: 2, 
                }
            ],
          }, 
        }); //Constructor Chart

        console.log(grafico);
      }); //Evento DOMContentLoaded
    </script>
  </body>
</html>