<template>
    <v-container-fluid>
        <v-card
        class="d-flex justify-space-between mb-6"
        flat
        tile
        >
            <v-card
            class="pa-2"
            flat
            tile
            >
            <div class="display-1">Guru</div>
            </v-card>
            <v-card
            class="pa-2"
            flat
            tile
            >
            <a href="#" class="font-italic" style="color:#4380B9;" >
                Download Template Excel
                <v-icon color="#4380B9"
                    right
                >
                    mdi-arrow-down-bold
                </v-icon>
            </a>
            <v-btn
            depressed
            color="#4380B9"
            rounded
            dark
            class="text-capitalize ml-7"
            >
            Upload Excel 
            <v-icon
                right
                dark
            >
                mdi-file-excel
            </v-icon>
            </v-btn>
            </v-card>
        </v-card>  
    </v-container-fluid>
</template>
