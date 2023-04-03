<Datatable>
<template>
    <v-container>
        <v-data-table>
            <template v-slot:top>
                <v-toolbar flat>
                    <v-toolbar-title></v-toolbar-title>
                    <!-- v-divider :  -  insert vertical :  -->
                    <v-divider class="mx-4" insert vertical></v-divider>
                    <v-spacer></v-spacer>
                    <!-- v-dioalog :  -->
                    <v-dialog v-model="dialog" max-width="500px">
                        <template v-slot:activator="{on,attrs}">
                            <v-btn color="primary" dark class="mb-2" v-bind="attrs" v-on="on"></v-btn>
                        </template>
                        <!-- v-card :  -->
                        <v-card>
                            <v-card-title>
                                <span class="text-h5"></span>
                            </v-card-title>
                            <v-card-text>
                                <v-container>
                                    <v-row></v-row>
                                </v-container>
                            </v-card-text>
                            <v-card-actions>
                                <v-spacer></v-spacer>
                                <v-btn color="blue darken-1" text>Cancel</v-btn>
                                <v-btn color="blue darken-1" text>Save</v-btn>
                            </v-card-actions>
                        </v-card>
                    </v-dialog>
                </v-toolbar>
            </template>
            <!-- v-slot :  -->
            <template template v-slot="{ item }">
                <!-- v-icon :  -->
                <v-icon small class="mr-2" @click="editItem(item)">mdi-pencil</v-icon>
                <v-icon small> mdi-delete </v-icon>
            </template>
        </v-data-table>
    </v-container>
</template>
</Datatable>

<script>
export default{
    // TodoItem : 
    name: 'TodoItem',

    data:() =>({
        //
        dialog:false,
        //
        headers:[],
        //
        editedItem:{},
    }),
    methods:{
        editItem(item){
            //JSON.parse :
            this.editedItem=JSON.parse(JSON.stringify(item));
            this.dialog=true;
        },
    },
    mounted() {},
};
</script>
<!-- scoped :  -->
<style scoped>
</style>