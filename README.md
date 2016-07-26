# Magento Front End Developper exam study guide
## 1. Use the Magento Design Fallback System

Exam proportion: 7%.

#### 1.1. Create custom themes

Magento templates, layouts and themes translations under :

`app/design/{package}/{theme}/`   

Magento skins files :

`skin/frontend/{package}/{theme}/`

For create a theme (exemple : mypackage) you need to create the following :

`app/design/mypackage/default/layout`     
`app/design/mypackage/default/template`  
`app/design/mypackage/default/locale`

&

`skin/frontend/mypackage/default/css`     
`skin/frontend/mypackage/default/images`    
`skin/frontend/mypackage/default/js`   


Next create a local.xml in layout for update or change default theme layout.    
`app/design/mypackage/default/layout/local.xml`


> Never touch the `base/default` you need it for the fallback system


![alt text](/common/images/admin-design-package.png "Admin design package")

#### 1.2 Configure design fallback using the options found on the admin panel under *System > Configuration > Design*

###### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1.2.1 Design Package

###### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1.2.2 Default Theme

###### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1.2.3 Type-specific Themes

###### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1.2.4 Design exceptions

#### 1.3 Apply a temporary theme configuration to a store view using the options found in the Admin panel under *System > Design*

#### 1.4 Understand the difference and similarities between *System > Configuration > Design* and *System > Design* to configure the design fallback


## 2. Use Layout XML to Customize a Theme

Exam proportion: (19%)

## 3. Create and Customize Template Files

Exam proportion: (16%)

## 4. Effectively Use the Magento Block-Template Design System

Exam proportion: (11%)

## 5. Identify Where to Locate Files and Create New Files in the Theming-related Directory Structure

Exam proportion: (7%)

## 6. Customize and Create JavaScript Within the Magento Framework

Exam proportion: (8%)

## 7. Use CSS Effectively to Customize Magento Look and Feel

Exam proportion: (9%)

## 8. Customize the Look and Feel of Specific Magento Pages

Exam proportion: (12%)

## 9. Correctly Use the Admin Configuration Scopes (Default/Website/Store View Fallback)

Exam proportion: (6%)

## 10. Implement Internationalization of Frontend Pages (CE + EE)

Exam proportion: (4%)





References : http://blog.belvg.com/create-custom-themes-magento-front-end-developer-certification.html
