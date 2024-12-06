
<template>
    <section class="desktop-view mx-44 my-10 space-y-24 ">
        <a :href="`/perfil?${worker.id}`" class="result-item" v-for="worker in workers" :key="worker.id">
            <div class="result-item border border-black shadow-md rounded-lg">
                <div class="available-badge">Disponible</div>
                    <div class="result-content my-4 mx-7">
                        <div class="text-content">
                            <h3 class="font-bold">{{ worker.fullName }}</h3>
                            <p class="parrafo">{{ worker.job }}</p>
                        <div class="rating">
                            <span>⭐ 4.5 / 5.0</span>
                        </div>
                            <button class="contact-btn"><i class="fab fa-whatsapp"></i> Contactar</button>
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
            <div class="available-badge">Disponible</div>
            <div class="result-content my-4 mx-7">
                <div class="text-content">
                <h3 class="font-bold">{{ worker.fullName }}</h3>
                <p class="parrafo">{{ worker.job }}</p>
                <div class="rating">
                    <span>⭐ 4.5 / 5.0</span>
                </div>
                <button class="contact-btn"><i class="fab fa-whatsapp"></i> Contactar</button>
                </div>
                <div class="image-content">
                <img :src="worker.photo" :alt="`Foto de ${worker.fullName}`">
                </div>
            </div>
            </div>
        </a>
    </section>
</template>

<script>

export default {
    data() {
        return {
            workers: []
        };
    },
    created() {
        console.log('Componente Prueba.vue creado');
        console.log('Obteniendo resultados...');
        console.log(window.location.href);
        this.obtenerResultados();
    },
    methods: {
        async obtenerResultados() {
            try {
                const localUrl = window.location.search;
                const searchParams = new URLSearchParams(localUrl);
                const category = searchParams.get('category');
                const service = searchParams.get('service') || '';
                const response = await fetch(`http://localhost:3000/api/workers/category/${category}?search=${service}`);
                const data = await response.json();
                this.workers = data;
            } catch (error) {
                console.error('Error al obtener los resultados:', error);
            }
        }
    }
};
</script>

<style>
.parrafo{
    width: 300px;
    overflow: hidden;
    display: -webkit-box; 
    -webkit-line-clamp: 3; 
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