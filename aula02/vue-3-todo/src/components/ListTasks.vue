<template>
  <div>
    <v-text-field clearable label="Add Task"></v-text-field>

    <v-list lines="three" select-strategy="classic">
      <v-list-subheader>General</v-list-subheader>
      
        <v-list-item
          v-for="item in settingsItems"
          :key="item.value"
          :subtitle="item.subtitle"
          :title="item.title"
          :value="item.value"
        >
          <template v-slot:prepend="{ isSelected, select }">
            <v-list-item-action start>
              <v-checkbox-btn :model-value="isSelected" @update:model-value="select"></v-checkbox-btn>
            </v-list-item-action>
          </template>
        </v-list-item>
    </v-list>
  </div>
</template>
 
<script setup>
const tasks = [
  {
    title: "Estudar Vue",
    description: "Estudar vue com Vuetify"
  }
]
</script>
