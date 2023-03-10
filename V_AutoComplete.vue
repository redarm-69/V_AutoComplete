<template>
    <div class="autocomplete">
        <input type="search" class="form-control" :value="searchText" @input="onInput" :placeholder="placeholder"
            :required="required">
        <ul class="dropdown-menu" v-show="filteredItems.length > 0 && searchText.length > 0">
            <li v-for="item in filteredItems" :key="item" @click="selectItem(item)">{{ item }}</li>
        </ul>
    </div>
</template>
  
<script>
export default {
    props: {
        items: {
            type: Array,
            required: true
        },
        required: {
            type: Boolean, 
            default: false
        },
        placeholder: {
            type: String,
            default: ''
        },
        modelValue: {
            type: String,
            default: ''
        },
        onUpdateModelValue: {
            type: Function
        },
    },
    emits: ["update:modelValue"],
    data() {
        return {
            searchText: this.modelValue,
            filteredItems: []
        };
    },
    watch: {
        modelValue(newValue) {
            this.searchText = newValue;
        },
    },
    methods: {
        onInput(e) {
            // this.$emit('onInput', e.target.value);
            this.searchText = e.target.value;
            this.$emit('update:modelValue', this.searchText);
            if (typeof this.onUpdateModelValue === 'function') {
                this.onUpdateModelValue(e.target.value);
            }
            this.filteredItems = this.items.filter(item =>
                item.toLowerCase().includes(this.searchText.toLowerCase())
            );

        },
        selectItem(item) {
            this.searchText = item;
            this.filteredItems = [];
            this.$emit('update:modelValue', this.searchText);
        }
    }
};
</script>
  
<style>
.autocomplete {
    position: relative;
}

.dropdown-menu {
    position: absolute;
    z-index: 1000;
    display: block;
    margin: 0;
    padding: 0;
    list-style: none;
    background-color: #fff;
    border: 1px solid rgba(0, 0, 0, 0.15);
    border-radius: 0.25rem;
}

.dropdown-menu>li {
    padding: 3px 20px;
    cursor: pointer;
    user-select: none;
}

.dropdown-menu>li:hover,
.dropdown-menu>li:focus {
    background-color: #f1f1f1;
}
</style>
  
