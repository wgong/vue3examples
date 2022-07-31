<script>
/* DEBUG

*/
import TreeView from './components/TreeView.vue' 
import MarkdownEditor from './components/MarkdownEditor.vue'

import HelloWorld from './components/HelloWorld.vue'
import GuiCounter from './components/GuiCounter.vue'
import GuiCells from './components/GuiCells.vue'
import GuiTempConverter from './components/GuiTempConverter.vue'
import AttributeBinding from './components/AttributeBinding.vue'
import LoopsAndConditionals from './components/LoopsAndConditionals.vue'
import UserInput from './components/UserInput.vue'
import FormBindings from './components/FormBindings.vue'
import SimpleComponent from './components/SimpleComponent.vue'
import RandomUser from './components/RandomUser.vue'
import TodoMVC from './components/TodoMVC.vue'
import TodoMVC2 from './components/TodoMVC2.vue'
import GuiFlightBooker from './components/GuiFlightBooker.vue'
import GuiTimer from './components/GuiTimer.vue'
import GuiCRUD from './components/GuiCRUD.vue'
import GuiCircleDrawer from './components/GuiCircleDrawer.vue'
import FetchGitHub from './components/FetchGitHub.vue'
import SimpleGrid from './components/SimpleGrid.vue'



export default {
  name: 'App',
  data() {
    return {
      selectedComp: "HelloWorld",
    }
  },
  components: {
    /* DEBUG


    */
    TreeView,
    MarkdownEditor,
    AttributeBinding,
    LoopsAndConditionals,
    UserInput,
    FormBindings,
    SimpleComponent,
    RandomUser,
    TodoMVC,
    TodoMVC2,
    GuiCircleDrawer,
    FetchGitHub,
    SimpleGrid,
    GuiFlightBooker,
    GuiTimer,
    GuiCRUD,
    GuiCounter,
    GuiCells,
    GuiTempConverter,
    HelloWorld,
  }
}
</script>

<template>
<h2>Vue-3 Examples</h2>
<div>
Select component to demo (suffix 2 for options API):
  <select id="select-comp" v-model="selectedComp">
    <option>HelloWorld</option>
    <option>LoopsAndConditionals</option>

    <option>UserInput</option>
    <option>FormBindings</option>
    <option>AttributeBinding</option>

    <option>SimpleComponent</option>
    <option>SimpleGrid</option>

    <option>TodoMVC</option>
    <option>TodoMVC2</option>

    <option>RandomUser</option>
    <option>FetchGitHub</option>
    
    <option>MarkdownEditor</option>
    <option>TreeView</option>

    <option>GuiCounter</option>
    <option>GuiCells</option>
    <option>GuiTempConverter</option>
    <option>GuiTimer</option>
    <option>GuiFlightBooker</option>
    <option>GuiCRUD</option>
    <option>GuiCircleDrawer</option>


<!--  DEBUG

  
-->    
  </select>

</div>
<hr>



  <GuiCounter v-if="selectedComp === 'GuiCounter'"/>
  <GuiCells v-if="selectedComp === 'GuiCells'"/>
  <GuiTempConverter v-else-if="selectedComp === 'GuiTempConverter'"/>
  <AttributeBinding v-else-if="selectedComp === 'AttributeBinding'"/>
  <LoopsAndConditionals v-else-if="selectedComp === 'LoopsAndConditionals'"/>
  <UserInput v-else-if="selectedComp === 'UserInput'" />
  <FormBindings v-else-if="selectedComp === 'FormBindings'"/>
  <SimpleComponent v-else-if="selectedComp === 'SimpleComponent'"/>
  <RandomUser v-else-if="selectedComp === 'RandomUser'"/>
  <TodoMVC v-else-if="selectedComp === 'TodoMVC'"/>
  <TodoMVC2 v-else-if="selectedComp === 'TodoMVC2'"/>
  <GuiFlightBooker v-else-if="selectedComp === 'GuiFlightBooker'"/>
  <GuiTimer v-else-if="selectedComp === 'GuiTimer'"/>
  <GuiCRUD v-else-if="selectedComp === 'GuiCRUD'"/>
  <GuiCircleDrawer v-else-if="selectedComp === 'GuiCircleDrawer'"/>
  <FetchGitHub v-else-if="selectedComp === 'FetchGitHub'"/>
  <SimpleGrid v-else-if="selectedComp === 'SimpleGrid'"/> 
  <MarkdownEditor v-else-if="selectedComp === 'MarkdownEditor'"/> 

  <TreeView v-else-if="selectedComp === 'TreeView'"/>   
  
<!--  DEBUG
-->  



<HelloWorld v-else msg="Welcome to Your Vue.js App"/>







<!--
      <img alt="Vue logo" src="./assets/logo.png" width="50">

-->


</template>



<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
  margin-top: 20px;
}
</style>
