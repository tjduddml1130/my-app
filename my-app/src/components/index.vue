<template>
  <div>
    <h3>그리드 컴포넌트 분리 예제</h3>
     <form id="search">
    Search <input name="query" v-model="searchQuery">
    </form>

    <grid-temp :data="gridData" :columns="gridColumns" :filter-key="searchQuery"></grid-temp>
    <TreeTemp :model="treeData" ></TreeTemp>
  <ul>
  <item
    class="item"
    :model="treeData">
  </item>
</ul>
  </div>

</template>

<script>
import GridTemp from "./GridTemp";
import TreeTemp from "./TreeTemp2";
import jstree from "./jstree";
export default {

  
  data: function() {
    return {
      searchQuery: "",
      gridColumns: ["LISTNUM", "CDTYPEK", "CDCODEIDK"],
      gridData: [
        { LISTNUM: 1, CDTYPEK: "000001", CDCODEIDK: "test01" },
        { LISTNUM: 2, CDTYPEK: "000002", CDCODEIDK: "test02" },
        { LISTNUM: 3, CDTYPEK: "000003", CDCODEIDK: "test03" },
        { LISTNUM: 4, CDTYPEK: "000004", CDCODEIDK: "test04" }
      ],
        treeData: {
          name: 'My Tree',
          children: [
            { name: 'hello' },
            { name: 'wat' },
            {
              name: 'child folder',
              children: [
                {
                  name: 'child folder',
                  children: [
                    { name: 'hello' },
                    { name: 'wat' }
                  ]
                },
                { name: 'hello' },
                { name: 'wat' },
                {
                  name: 'child folder',
                  children: [
                    { name: 'hello' },
                    { name: 'wat' }
                  ]
                }
              ]
            }
          ]
        },
        treeData: {
                name: 'Todos-client',
                children: [
                    { name: 'assets', 
                      children:[
                          {name: 'logo.png' }
                      ]
                    },
                    { name: 'components', 
                      children: [
                        { name: 'GridTemp.vue' },
                        { name: 'HelloVorld.vue' },
                        { name: 'TestMenu.vue' },
                        { name: 'TreeTemp.vue' }
                      ]
                    },
                    { name: 'router',
                      children: [
                        { name: 'index.js' }
                      ]
                    }
                ]
            }
      
    };
  },
  components: {
    GridTemp: GridTemp,
    jstree: jstree,
    TreeTemp: TreeTemp
  }
};
</script>

<style>
</style>
