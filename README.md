# V_AutoComplete
Vue AutoComplete 

Using : 

# Import
    import V_AutoComplete from "./V_AutoComplete.vue";

# Components
    components: {
      V_AutoComplete,
    },

# data
    data() {
        return {
            Rows: [],
            SelectedValue: "",
        };
    },
    
# template
    <V_AutoComplete :items="Rows" v-model="SelectedValue"></V_AutoComplete>


