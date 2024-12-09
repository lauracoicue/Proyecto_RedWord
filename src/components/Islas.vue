
<template>
    <section class="desktop-view  columns-2 mx-44 my-10 space-y-24 ">
        <a :href="`/perfil?${worker.id}`" class="result-item" v-for="worker in workers" :key="worker.id">
            <div class="result-item border border-black shadow-md rounded-lg">
                <div 
                    class="available-badge" 
                    :class="{'fade-in': worker.isAvailable, 'fade-out': !worker.isAvailable }" 
                    v-if="worker.isAvailable">
                    Disponible
                </div>

                    <div class="result-content my-4 mx-7">
                        <div class="text-content">
                            <h3 class="font-bold">{{ worker.fullName }}</h3>
                            <p class="parrafo">{{ worker.job }}</p>
                        <div class="rating">
                            <span>⭐ 4.5 / 5.0</span>
                        </div>
                            <button class="contact-btn"><i class="fab fa-whatsapp "></i> Contactar</button>
                        </div>
                        <div class="image-content">
                        <img :src="worker.photo" :alt="`Foto de ${worker.fullName}`">
                    </div>
                </div>
            </div>
        </a>
    </section>
    
     <section class="mobile-view mx-44 my-16">
        <a :href="`/perfil?${worker.id}`" class="result-item" v-for="worker in workers" :key="worker.id">
            <div class="result-item border border-black rounded-lg">
                <div
                    class="available-badge" 
                    :class="{ 'fade-in': worker.isAvailable, 'fade-out': !worker.isAvailable }" 
                    v-if="worker.isAvailable">
                    Disponible
                </div>
            <div class="result-content my-4 mx-7">
                <div class="text-content">
                <h3 class="font-bold">{{ worker.fullName }}</h3>
                <p class="parrafo">{{ worker.job }}</p>
                <div class="rating">
                    <span>⭐ 4.5 / 5.0</span>
                </div>
                <a :href="link">
                    <button class="bg-green-500 text-white font-bold text-center text-xs p-2 rounded-full w-30">
                    <svg
                        xmlns="http://www.w3.org/2000/svg"
                        x="0px"
                        y="0px"
                        width="100"
                        height="100"
                        viewBox="0 0 48 48"
                        class="size-7 absolute text-white mx-2 -my-1/2"
                    >
                        <path
                        fill="#fff"
                        d="M4.868,43.303l2.694-9.835C5.9,30.59,5.026,27.324,5.027,23.979C5.032,13.514,13.548,5,24.014,5c5.079,0.002,9.845,1.979,13.43,5.566c3.584,3.588,5.558,8.356,5.556,13.428c-0.004,10.465-8.522,18.98-18.986,18.98c-0.001,0,0,0,0,0h-0.008c-3.177-0.001-6.3-0.798-9.073-2.311L4.868,43.303z"
                        ></path>
                        <path
                        fill="#fff"
                        d="M4.868,43.803c-0.132,0-0.26-0.052-0.355-0.148c-0.125-0.127-0.174-0.312-0.127-0.483l2.639-9.636c-1.636-2.906-2.499-6.206-2.497-9.556C4.532,13.238,13.273,4.5,24.014,4.5c5.21,0.002,10.105,2.031,13.784,5.713c3.679,3.683,5.704,8.577,5.702,13.781c-0.004,10.741-8.746,19.48-19.486,19.48c-3.189-0.001-6.344-0.788-9.144-2.277l-9.875,2.589C4.953,43.798,4.911,43.803,4.868,43.803z"
                        ></path>
                        <path
                        fill="#cfd8dc"
                        d="M24.014,5c5.079,0.002,9.845,1.979,13.43,5.566c3.584,3.588,5.558,8.356,5.556,13.428c-0.004,10.465-8.522,18.98-18.986,18.98h-0.008c-3.177-0.001-6.3-0.798-9.073-2.311L4.868,43.303l2.694-9.835C5.9,30.59,5.026,27.324,5.027,23.979C5.032,13.514,13.548,5,24.014,5 M24.014,42.974C24.014,42.974,24.014,42.974,24.014,42.974C24.014,42.974,24.014,42.974,24.014,42.974 M24.014,42.974C24.014,42.974,24.014,42.974,24.014,42.974C24.014,42.974,24.014,42.974,24.014,42.974 M24.014,4C24.014,4,24.014,4,24.014,4C12.998,4,4.032,12.962,4.027,23.979c-0.001,3.367,0.849,6.685,2.461,9.622l-2.585,9.439c-0.094,0.345,0.002,0.713,0.254,0.967c0.19,0.192,0.447,0.297,0.711,0.297c0.085,0,0.17-0.011,0.254-0.033l9.687-2.54c2.828,1.468,5.998,2.243,9.197,2.244c11.024,0,19.99-8.963,19.995-19.98c0.002-5.339-2.075-10.359-5.848-14.135C34.378,6.083,29.357,4.002,24.014,4L24.014,4z"
                        ></path>
                        <path
                        fill="#40c351"
                        d="M35.176,12.832c-2.98-2.982-6.941-4.625-11.157-4.626c-8.704,0-15.783,7.076-15.787,15.774c-0.001,2.981,0.833,5.883,2.413,8.396l0.376,0.597l-1.595,5.821l5.973-1.566l0.577,0.342c2.422,1.438,5.2,2.198,8.032,2.199h0.006c8.698,0,15.777-7.077,15.78-15.776C39.795,19.778,38.156,15.814,35.176,12.832z"
                        ></path>
                        <path
                        fill="#fff"
                        fill-rule="evenodd"
                        d="M19.268,16.045c-0.355-0.79-0.729-0.806-1.068-0.82c-0.277-0.012-0.593-0.011-0.909-0.011c-0.316,0-0.83,0.119-1.265,0.594c-0.435,0.475-1.661,1.622-1.661,3.956c0,2.334,1.7,4.59,1.937,4.906c0.237,0.316,3.282,5.259,8.104,7.161c4.007,1.58,4.823,1.266,5.693,1.187c0.87-0.079,2.807-1.147,3.202-2.255c0.395-1.108,0.395-2.057,0.277-2.255c-0.119-0.198-0.435-0.316-0.909-0.554s-2.807-1.385-3.242-1.543c-0.435-0.158-0.751-0.237-1.068,0.238c-0.316,0.474-1.225,1.543-1.502,1.859c-0.277,0.317-0.554,0.357-1.028,0.119c-0.474-0.238-2.002-0.738-3.815-2.354c-1.41-1.257-2.362-2.81-2.639-3.285c-0.277-0.474-0.03-0.731,0.208-0.968c0.213-0.213,0.474-0.554,0.712-0.831c0.237-0.277,0.316-0.475,0.474-0.791c0.158-0.317,0.079-0.594-0.04-0.831C20.612,19.329,19.69,16.983,19.268,16.045z"
                        clip-rule="evenodd"
                        ></path>
                    </svg>
                    <h1 class="mx-10 text-lg">Contactar</h1>
                    </button>
                </a>
                </div>
                <div class="image-content -my-6">
                <img :src="worker.photo" :alt="`Foto de ${worker.fullName}`">
                </div>
            </div>
            </div>
        </a>
    </section>
</template>


<script>

import { io } from "socket.io-client"; // Importar Socket.IO client

export default {
    data() {
        return {
            workers: [], 
            socket: null, 
        };
    },
    created() {
        this.obtenerResultados();
    },
    methods: {
        async obtenerResultados() {
            try {
                const localUrl = window.location.search;
                const searchParams = new URLSearchParams(localUrl);
                const category = searchParams.get("category");
                const service = searchParams.get("service") || "";

                console.log("Categoría:", category, "Servicio:", service);  
               
                const response = await fetch(
                    `http://localhost:3000/api/workers/category/${category}?search=${service}`
                );
                const { refreshResult, channel, data, client } = await response.json();
                console.log("Datos obtenidos:", refreshResult, channel, data, client );
                this.workers = data;
                console.log("Resultados:", data);   
                this.iniciarSocket(refreshResult, channel, client);
            } catch (error) {
                console.error("Error al obtener los resultados:", error);
            }
        },
        iniciarSocket(host, channel, id) {
            console.log("Conectando al socket:", host, "canal:", channel, "id:", id);
            this.socket = io(host, {
                query: {
                    id: id,
                },
                transports: ["websocket"]
            });
            this.socket.on(channel, (newData) => {
                console.log("Actualización recibida del socket:", newData);
                this.workers = this.workers.map((worker) => {
                    if (worker.id === newData.id) {
                        worker.isAvailable = newData.isAvailable;
                    }
                    return worker;
                });
                
            });

        },
    },
    beforeDestroy() {
        if (this.socket) {
            this.socket.disconnect();
        }
    },
};
</script>

<style>

.fade-in {
    opacity: 1;
    transition: opacity 0.3s ease-in;
}

.fade-out {
    opacity: 0;
    transition: opacity 0.3s ease-out;
}

.parrafo{
    width: 300px;
    overflow: hidden;
    display: -webkit-box; 
    -webkit-box-orient: vertical; 
    text-overflow: ellipsis; 
    white-space: normal;
}
.result-item{
    display: grid;
    --tw-shadow: 0 1px 2px 0 rgb(0 0 0 / 0.05);
    --tw-shadow-colored: 0 1px 2px 0 var(--tw-shadow-color);
    box-shadow: var(--tw-ring-offset-shadow, 0 0 #0000), var(--tw-ring-shadow, 0 0 #0000), var(--tw-shadow);
    
}
.result-item {
    break-inside: avoid; /* Evita que las tarjetas se partan */
}

    @media screen and (max-width: 1024px) {    .desktop-view {
            display: none;    }
    }
	@media screen and (min-width: 1023px) {    .mobile-view {
			display: none;    }
	}

</style>

<!---
<style scoped>

/* Resultados */
.results {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 2em;
    padding: 2em;
}

/* Ajustes responsivos */
@media (max-width: 768px) {
    .results {
        grid-template-columns: 1fr; /* Una sola columna para pantallas pequeñas */
    }
    
    .result-item {
        max-width: 100%; /* Las tarjetas ocupan todo el ancho en pantallas pequeñas */
    }
}

/* Contenedor de la tarjeta de resultados */
.result-item {
    display: flex;
    flex-direction: column;
    gap: 1em;
    justify-content: space-between;
    align-items: center;
    padding: 1em;
    background-color: white;
    border-radius: 10px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
    margin-bottom: 20px;
    position: relative;
    max-width: 600px; /* Ajusta esto para pantallas más grandes */
    max-height: 300px; /* Ajusta esto para pantallas más grandes */
}
</style>
  --->