<template>
<div>
    <form id="search">
        Search <input name="query" v-model="searchQuery">
    </form>
    <GridTemp :data="gridData" :columns="gridColumns" :filter-key="searchQuery"></GridTemp>
    <TreeTemp :model="treeData"></TreeTemp>
    <ul>
        <TreeTemp2 :model="treeData"></TreeTemp2>
    </ul>
    <polygraph width="200" height="200"></polygraph>
</div>    
</template>

<script>
import GridTemp from '@/components/GridTemp'
import TreeTemp from '@/components/TreeTemp'
import TreeTemp2 from '@/components/TreeTemp2'
import polygraph from '@/components/polygraph'

export default {
    data() {
        return {
            searchQuery: '',
            gridColumns: ['listNum', 'cdTitle', 'fileName', 'insertUserId', 'cdOrgName','updateDate'],
            gridData: [
                {
                listNum: 1,
                cdTitle: '테스트 공지1',
                fileName: 'log4j.xml',
                insertUserId: 'admin',
                cdOrgName: '시스템관리자',
                updateDate: '2018.01.01 01:01:01'
              },
              {
                listNum: 2,
                cdTitle: '테스트 공지2',
                fileName: 'log4j.xml',
                insertUserId: 'admin',
                cdOrgName: '시스템관리자',
                updateDate: '2018.02.02 02:02:02'
              },
              {
                listNum: 3,
                cdTitle: '테스트 공지3',
                fileName: 'log4j.xml',
                insertUserId: 'admin',
                cdOrgName: '시스템관리자',
                updateDate: '2018.03.03 03:03:03'
              },
              {
                listNum: 4,
                cdTitle: '테스트 공지4',
                fileName: 'log4j.xml',
                insertUserId: 'admin',
                cdOrgName: '시스템관리자',
                updateDate: '2018.12.06 14:08:00'
              },
              {
                listNum: 5,
                cdTitle: '테스트 공지5',
                fileName: 'log4j.xml',
                insertUserId: 'admin',
                cdOrgName: '시스템관리자',
                updateDate: '2018.12.06 14:08:00'
              }
            ],
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
        }
    },
    components: {
        GridTemp,
        TreeTemp,
        TreeTemp2,
        polygraph
    }
}
</script>

<style>

</style>
