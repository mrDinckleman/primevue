<template>
    <DocSectionText v-bind="$attrs">
        <p>Checkboxes can be generated using a list of values.</p>
    </DocSectionText>
    <div class="card flex justify-center">
        <div class="flex flex-col gap-4">
            <div v-for="category of categories" :key="category.key" class="flex items-center gap-2">
                <Checkbox v-model="selectedCategories" :inputId="category.key" name="category" :value="category.name" />
                <label :for="category.key">{{ category.name }}</label>
            </div>
        </div>
    </div>
    <DocSectionCode :code="code" />
</template>

<script setup lang="ts">
import Checkbox from '@/volt/Checkbox.vue';
import { ref } from 'vue';

const selectedCategories = ref(['Marketing']);
const categories = ref([
    { name: 'Accounting', key: 'A' },
    { name: 'Marketing', key: 'M' },
    { name: 'Production', key: 'P' },
    { name: 'Research', key: 'R' }
]);

const code = ref(`
<template>
    <div class="card flex justify-center">
        <div class="flex flex-col gap-4">
            <div v-for="category of categories" :key="category.key" class="flex items-center gap-2">
                <Checkbox v-model="selectedCategories" :inputId="category.key" name="category" :value="category.name" />
                <label :for="category.key">{{ category.name }}</label>
            </div>
        </div>
    </div>
</template>

<script setup lang="ts">
import Checkbox from '@/volt/Checkbox.vue';
import { ref } from 'vue';

const selectedCategories = ref(['Marketing']);
const categories = ref([
    { name: 'Accounting', key: 'A' },
    { name: 'Marketing', key: 'M' },
    { name: 'Production', key: 'P' },
    { name: 'Research', key: 'R' }
]);
<\/script>
`);
</script>
