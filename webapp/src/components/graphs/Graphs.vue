/** Copyright 2021 Tianshu AI Platform. All Rights Reserved.
 *
 * Licensed under the Apache License, Version 2.0 (the "License");
 * you may not use this file except in compliance with the License.
 * You may obtain a copy of the License at
 *
 *     http://www.apache.org/licenses/LICENSE-2.0
 *
 * Unless required by applicable law or agreed to in writing, software
 * distributed under the License is distributed on an "AS IS" BASIS,
 * WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
 * See the License for the specific language governing permissions and
 * limitations under the License.
 * =============================================================
 */

<template>
  <component :is="this.getCurTag=='c_graph'?'C_Graphs':'S_Graphs'"/>
</template>
<script>
import S_Graphs from './S_Graphs.vue';
import C_Graphs from './C_Graphs.vue';
import { createNamespacedHelpers } from "vuex";
const {mapGetters: mapGraphGetters} = createNamespacedHelpers("graph");
export default {
  name: "Graph",
  computed: {
    ...mapGraphGetters(["getCurTag"])
  },
  components:{
    S_Graphs,
    C_Graphs
  }
}
</script>