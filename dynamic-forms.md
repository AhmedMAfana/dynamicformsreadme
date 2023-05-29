# ![How to use dynamic Forms]


For use dynamic Forms we have custom package to handle inputs type and validation

   
    
## Form Composition 
   The dynamic form component <dynamic-form /> takes 
    
    Props :form as object this object restricted to specific format
    Emits   @error , @openModal , @submitted
    
    
## How to use <dynamic-form /> component 
    
The dynamic form component <dynamic-form /> is straight-forward You will only need to add it to your template like this:
    
      <template>
           <dynamic-form :form="form" />
      </template>
      
  To define form object we have many input Fields type 
   - Text
   - Email
   - Password
   - Url
   - Number
   - Checkbox
   - Radio
   - Select
   - Textarea
   - SelectCustomField
   - DateField
   - FileField
   - MultiplePhoneField
   - MultipleEmailsField
   - SelectWithButtonsField
   - SelectWithGroupsField
      
    <script setup lang="ts">
      const form =  reactive({
        id : 'your module name or what ever u need' ,
        groups :[
         {
          legend: 'name of ur group' ,
           fields: {
                 first_name: TextField({
                 label: 'First Name',
                 showMode : 'small'
            }),
           }
         }
        ]
      });
    </script>
