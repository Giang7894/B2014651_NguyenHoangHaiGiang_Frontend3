<script>
export default{
    props: {
        modelValue: {type: String, default: ""}
    },
    emits: ["submit","update:modelValue"],
    methods: {
        updateModelValue(e){
            this.$emit("updatemodelValue",e.target.value);
        },

        submit(){
            this.$emit("submit");
        },
    },
};
</script>

<template>
    <div class="inpu-group">
        <input type="text" class="from-control" placeholder="Nhập thông tin cần tìm" :value="modelValue" @input="updateModelValue" @key.enter="submit"/>
        <div class="input-group-append">
            <button class="btn btn-outline-secondary" type="button" @click="submit">
                <i class="fas fa-search"></i> Tìm kiếm
            </button>
        </div>
    </div>
</template>

