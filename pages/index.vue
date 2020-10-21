<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
      <v-list-item-group>
        <draggable :list="stuff">
          <v-list-item v-for="(item, index) in stuff" :key="index">
            <v-list-item-content :value="item.itemName">
              {{ item }}
              <v-list-item-icon>
                <v-icon color="red lighten-3" @click="removeItem(index)">
                  mdi-trash-can-outline
                </v-icon>
              </v-list-item-icon>
            </v-list-item-content>
          </v-list-item>
        </draggable>
      </v-list-item-group>
    </v-col>
  </v-row>
</template>

<script>
import draggable from 'vuedraggable'

export default {
  components: {
    draggable,
  },

  data() {
    return {
      stuff: [
        'one',
        'two',
        'three',
        'four',
        'five',
        'six',
        'seven',
        'eight',
        'nine',
        'ten',
      ],
    }
  },

  methods: {
    removeItem(index) {
      this.stuff.splice(index, 1)
    },
  },
}
</script>
