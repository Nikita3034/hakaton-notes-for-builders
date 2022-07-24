<template>
    <div class="modal" v-if="$parent.isModalOpen">
        <div class="info" :class="item['status'] === 1 ? 'success' : item['status'] === 2 ? 'error' : 'between'">
            <a class="close-button" @click="$parent.isModalOpen = !$parent.isModalOpen">
                x
            </a>
            <div class="item">
                <div>{{ item.name }}</div>
                <div>{{ item.executor }}</div>
            </div>
        </div>
    </div>
</template>

<script>
export default ({
    props: {
        item: Object
    },
    methods: {
		hide() {
			this.$parent.isModalOpen = false;
		},
    }
})
</script>