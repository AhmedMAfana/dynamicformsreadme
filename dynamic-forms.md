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
      
     
call inputs type from   "@core/dynamic-forms"  like 
         
    import  {TextField} from "@core/dynamic-forms";
     
     
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
    
we have Validator type 
   - required
   - min
   - max
   - email
   - minLength
   - maxLength
   - pattern
   
import { Validator, required, email } from "@core/dynamic-forms"   

The Validator function takes 2 params, the validation function (required, min, max, email, etc) and the message to display when the validations are not successful:

      {
       email: EmailField({
           label: 'Email',
           validations: [
               Validator({ validator: required, text: 'This field is required' }),
               Validator({ validator: email, text: 'Format of email is incorrect' }),
           ],
       }),
      }


