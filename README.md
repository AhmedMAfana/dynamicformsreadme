# ![How to use dynamic Tables]


For use dynamic table we need 

    - Our main table component name  IndexFullTable 
       
    - A JS class as service extends from our main  DynamicService
    
## IndexFullTable component 
    this componant have two slots for inject modals
    #add-small-dialog
    #add-full-dialog

## DynamicService File 
    Takes two arguments it responsible for generate dynamic pinia store in run time and it include all logic for index , add ,edit ,delete action 
    1- first argument name of module it required as string  like 'categories' , 'products'
    2- second argument optional as object will inject in pinia store state  
    
    
 ### dynamic Tables usages
     1- create new page inside  pages  folder in project root let call it orders-page.vue
     
     2- inside orders-page  import our main dynamic table component  IndexFullTable   from "@/views/dashboards/dynamics/IndexFullTable.vue"; 
     
     3- create Ts class as child service  extends from DynamicService inside  service   folder in project root let call it OrderService.ts
     
     4- make new Instance for OrderService and pass first argument as 'orders' 
     
     5- create reactive varible require interface schema <ModuleMaterials>  and provide it for all child component 
     
     
 ## Example 
     <template>
       <IndexFullTable>
              <template #add-small-dialog>
                <small-modal />
              </template>
              <template #add-full-dialog>
                <large-modal />
              </template>
        </IndexFullTable>
    </template>
    
    <script setup lang="ts">
        const module = ref<string>('orders')
        const myInstance =  new OrderService(module.value ,{});
        const materials = reactive<ModuleMaterials>({
              module : module.value,
              form :  {},
              create_schema: {},
              create_form : {},
            })
            provide('moduleMaterials' , materials)
            provide('myInstance' , myInstance)
    </script>
    
    
    
    
    
    
    
