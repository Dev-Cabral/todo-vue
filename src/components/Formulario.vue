<script setup>
const props = defineProps(['cadastraTarefa', 'tarefaTemp', 'trocarFiltro', 'editaTareafaTemp'])
</script>

<template>
    <form @submit.prevent="props.cadastraTarefa">
        <div class="row">
            <div class="col">
                <input :value="props.tarefaTemp" @change="props.editaTareafaTemp " required
                    type="text" placeholder="Digite aqui a expressão da tarefa" class="form-control">
            </div>
            <div class="col-md-2">
                <button type="submit" class="btn btn-primary">Cadastrar</button>
            </div>
            <div class="col-md-2">
                <select @change="props.trocarFiltro" class="form-control">
                    <option value="todas ">Todas tarefas</option>
                    <option value="pendentes">pendentes</option>
                    <option value="finalizadas">finalizadas</option>
                </select>
            </div>
        </div>
    </form>
</template>

<style scoped>
    button, select {
        cursor: pointer;
    }
    
    option{
        cursor: pointer;
    }

@media (max-width: 760px) {
    .btn {
        margin-top: 6px;
        margin-bottom: 12px;
    }
}
</style>