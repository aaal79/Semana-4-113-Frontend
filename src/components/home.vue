<template>
<div>
    <div class="container-fluid">
        <div class="row mt-md-5 mt-sm-5 mt-xs-5">
            <div v-for="(art,indice) of datos" :key="art.id" class="col-lg-6 col-xs-12 border">
                <div v-if="indice<=3">
                <div  class="d-flex justify-content-center align-items-center">

                    <div class="p-3">
                       <svg width="12em" height="12em" viewBox="0 0 16 16" class="bi bi-alarm-fill" fill="currentColor" xmlns="http://www.w3.org/2000/svg">
                       <path fill-rule="evenodd" d="M6 .5a.5.5 0 0 1 .5-.5h3a.5.5 0 0 1 0 1H9v1.07a7.001 7.001 0 0 1 3.274 12.474l.601.602a.5.5 0 0 1-.707.708l-.746-.746A6.97 6.97 0 0 1 8 16a6.97 6.97 0 0 1-3.422-.892l-.746.746a.5.5 0 0 1-.707-.708l.602-.602A7.001 7.001 0 0 1 7 2.07V1h-.5A.5.5 0 0 1 6 .5zM.86 5.387A2.5 2.5 0 1 1 4.387 1.86 8.035 8.035 0 0 0 .86 5.387zM11.613 1.86a2.5 2.5 0 1 1 3.527 3.527 8.035 8.035 0 0 0-3.527-3.527zM8.5 5.5a.5.5 0 0 0-1 0v3.362l-1.429 2.38a.5.5 0 1 0 .858.515l1.5-2.5A.5.5 0 0 0 8.5 9V5.5z"
                            />
                        </svg>
                    </div>

                    <div class="p-2">
                        <p>
                            {{art.nombre}}
                        </p>
                    </div>

                </div>
                <div class="d-flex container-fluid justify-content-end pb-2 mt-n2">
                    <button type="button" class="btn btn-outline-info"> <a href="" target="_blank">Info>></a></button>
                </div>
                </div>
            </div>
        </div>
    </div>
    <div class="container-fluid">
        <div class="row justify-content-center mb-5">
            <div v-for="miembro in team" :key="miembro.codigo" class="col mt-5">
                     <div class="card text-white bg-dark">
                        <div class="d-flex justify-content-center p-2">
                            <img :src="miembro.image">
                        </div>
                        <div class="card-body">
                            <h5 class="card-title">CASO DE EXITO</h5>
                            <h5 class="card-title"> {{miembro.nombre}}</h5>
                            <p class="card-text">{{miembro.descripcion}}
                            </p>
                    </div>
                </div>
            </div>
        </div>
    </div>
    </div>
</template>


<script>
import axios from 'axios';
export default {
     data() {
        return {
            datos: null,
            team: [{
                nombre: '<<Telefónica>>',
                descripcion: 'Desde el área global de Supply Chain en Telefónica siempre nos hemos apoyado en la tecnología para mejorar nuestros procesos y lanzar nuevos proyectos. Y eso fue lo que nos ocurrió allá por 2018, cuando comenzamos a entender que ventajas nos traería el uso de la tecnología Blockchain. Cada uno alimenta con su información la vida de un equipo y la usa para optimizar sus operaciones. Conseguimos: Optimizar el inventario de equipos que tenemos, lo que nos lleva a algo muy importante optimizar el gasto, controlar el buen uso de nuestros equipos por todos los actores de la cadena, alertar sobre acciones que no sabíamos ni que ocurrían, adelantarnos a los problemas de los clientes para ofrecerles soluciones proactivas, Ser más sostenibles al mejorar la utilización del material que compramos. Todo con la seguridad, transparencia y fiabilidad que te da la tecnología Blockchain. "Difícilmente se hubiera conseguido de otra manera", afirma el gerente de operaciones.',
                image:"images/telefonica.jpg"
            }, {
                nombre: '<<Lotería de Navidad basada en blockchain, una realidad>>',
                descripcion: 'Hace prácticamente dos años fantaseábamos con la idea de una lotería nacional basada en una infraestructura tecnológica DLT. Pues ahora, de forma pionera en España, la administración de lotería El Negrito de Alicante se ha puesto manos a la obra y ha desarrollado la tecnología necesaria para gestionar las participaciones en el Sorteo de Navidad de a través de blockchain. El sorteo extraordinario de Navidad de la Lotería Nacional española no necesita mayor presentación, siendo uno de los sorteos con mayor tradición y más queridos del mundo. La novedad radica en la forma de tratar la gestión de las participaciones: la tecnología blockchain se pone al servicio de una lotería que será indiscutiblemente más segura. Para la gente que está al tanto de las evoluciones de la tecnología blockchain, la sorpresa será que hasta ahora apenas se había aplicado la DLT en el sector, y nunca en España. Sorprendente, sin duda, teniendo en cuenta las virtudes de la cadena de bloques a la hora de certificar transacciones de manera rápida, económica y segura.',
                image:"images/loteria.jpg"
            }, ]
        };
    },
    mounted() {
     axios.get('articulo/list')
    .then(response => (this.datos = response.data));

    },
    
}
</script>