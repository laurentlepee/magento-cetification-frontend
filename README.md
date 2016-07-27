# Magento Front End Developper study guide

Revision notes, links and docs for the Magento Front End Developer Certification exam.

## Chapters

### 1. Use the Magento Design Fallback System
---

Exam proportion: 7%.

1.1 Create custom themes

[//]: # (Magento templates, layouts and themes translations under :)
[//]: # (`app/design/{package}/{theme}/`   )
[//]: # (Magento skins files :)
[//]: # (`skin/frontend/{package}/{theme}/`)
[//]: # (For create a theme (exemple : mypackage) you need to create the following :)
[//]: # (`app/design/mypackage/default/layout`   )  
[//]: # (`app/design/mypackage/default/template`)  
[//]: # (`app/design/mypackage/default/locale`)
[//]: # (&)
[//]: # (`skin/frontend/mypackage/default/css`    )
[//]: # (`skin/frontend/mypackage/default/images`  )  
[//]: # (`skin/frontend/mypackage/default/js`   )
[//]: # (Next create a local.xml in layout for update or change default theme layout.   )
[//]: # (`app/design/mypackage/default/layout/local.xml`)
[//]: # (> Never touch the `base/default` you need it for the fallback system)
[//]: # (![alt text](/common/images/admin-design-package.png "Admin design package"))

1.2 Configure design fallback using the options found on the admin panel under *System > Configuration > Design*

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1.2.1 Design Package

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1.2.2 Default Theme

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1.2.3 Type-specific Themes

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1.2.4 Design exceptions

1.3 Apply a temporary theme configuration to a store view using the options found in the Admin panel under *System > Design*

1.4 Understand the difference and similarities between *System > Configuration > Design* and *System > Design* to configure the design fallback

**Links :**

*   [Creating a Magento theme from scratch](http://inchoo.net/magento/creating-a-new-magento-theme/)
*   [Magento Fallback Configuration](http://blog.belvg.com/magento-fallback-configuration-default-and-specific-themes-packages-design-exceptions-temporary-theme-configuration.html)
*  [Custom design fallbacks in Magento](https://fbrnc.net/blog/2012/03/custom-design-fallbacks-in-magento)

### 2. Use Layout XML to Customize a Theme
---

Exam proportion: (19%)

2.1 Demonstrate knowledge of all layout XML directives (layout handles, block, reference, action, remove, update and label)

2.2 Define an output block

2.3 Use a local.xml Files

2.4 Understand layout merging

2.5 Understand processing order of layout handles and other directives

2.6 Set values on block instances using layout XML

2.7 Move a child block from one parent to another using layout XML

2.8 Specify the root template for all pages or for specific pages

**Links :**
*  [Magento Layout XML Part 1](http://magebase.com/magento-tutorials/demystifying-magentos-layout-xml-part-1/)
*  [Magento Layout XML Part 2](http://magebase.com/magento-tutorials/digging-deeper-into-magentos-layout-xml-part-2/)
* [Using local.xml for overriding or updating xml structure](http://inchoo.net/magento/using-local-xml-for-overriding-or-updating-xml-structure/)
* [Layout XML Directives – Handles, Block, Reference, Action, Remove, Update](http://blog.belvg.com/layout-xml-directives-handles-block-reference-action-remove-update.html)
* [Use a Local.xml File](http://blog.belvg.com/use-a-local-xml-file.html)

### 3. Create and Customize Template Files
---

Exam proportion: (16%)

3.1 Assign a customized template file using layout XML

```xml
<?xml version="1.0"?>
<layout>
    <handle>
        <reference name="root">
            <action method="setTemplate"><template>page/template_file.phtml</template></action>
        </reference>
    </handle>
</layout>
```

3.2 Override a native template file with a customized template file, using the design fallback

`Same as theme fallback`

3.3 Describe conventions used in templates files :

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 3.3.1 Variable naming(_prefix for variables declared in a template)

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 3.3.2 PHP loop and block construct (for example: if(..): endif;)

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 3.3.3 Opening and closing PHP tags ( <?php vs <?, <% and others)

**Links :**
* [Template Variable Naming Conventions](http://magento-quickies.alanstorm.com/post/27440772714/template-variable-naming-conventions)
* [PHP tags](http://php.net/manual/en/language.basic-syntax.phptags.php)

### 4. Effectively Use the Magento Block-Template Design System
---

Exam proportion: (11%)

4.1 Declare a custon template using a core/template block via layout XML with a custom template, and output it as a child of a structural block or of a template block

```xml
<?xml version="1.0"?>
<layout>
    <default>
        <reference name="header">
            <block type="core/template" name="customblock" as="customblock" template="customblock/customblock.phtml"/>
        </reference>
    </default>
</layout>
```

4.2 Understand the differences between structural and content blocks

4.3 Assign a default root template on all pages

```xml
<?xml version="1.0"?>
<layout>
    <default>
        <reference name="root">
            <action method="setTemplate"><template>page/1column.phtml</template></action>
        </reference>
    </default>
</layout>
```

4.4 Assign a root template on a specific pages

Exemple catalog category pages :
```xml
<?xml version="1.0"?>
<layout>
    <catalog_category_view>
        <reference name="root">
            <action method="setTemplate"><template>page/2columns-left.phtml</template></action>
        </reference>
    </catalog_category_view>
</layout>
```

4.5 Demostrate the use of core/text_list blocks

`core/text_list`: Some blocks like content, left, right etc. are of type core/text_list. When these blocks are rendered, all their child blocks are rendered automatically without the need to call the `getChildHtml()` method.

**Links :**
* [Layout Element – . Block Type. Define an Output Block](http://blog.belvg.com/layout-element-block-type-define-an-output-block.html)
* [The most misunderstood concept in Magento](https://blog.philwinkle.com/the-most-misunderstood-concept-in-magento/)
* [Custom Block Development in Magento](http://code.tutsplus.com/tutorials/custom-block-development-in-magento--cms-23104)

### 5. Identify Where to Locate Files and Create New Files in the Theming-related Directory Structure
---

Exam proportion: (7%)

5.1 Describe the contents of the app/design and skin/directory branches and why they are separated

* `App/design` directory – Files that control how the page templates are rendered
* `Skin` directory – Files that control the visual aspects of the theme—CSS, images, etc

Magento breaks its theme files into separate directories like this to allow you more control over the security level of each directory on your server. The files in the skin directory need to be accessible to web browsers and need a very open permission setting. The files in the app/design directory only need to be accessible to the app and can be locked down further.

5.2 Describe the general directory hierarchy format under app/design and the skin

`app/design/mypackage/default/layout`  
`app/design/mypackage/default/template`   
`app/design/mypackage/default/locale`

&

`skin/frontend/mypackage/default/css`  
`skin/frontend/mypackage/default/images`  
`skin/frontend/mypackage/default/js`

**Links :**
* [Parent/Child Themes](http://alanstorm.com/magento_parent_child_themes)


### 6. Customize and Create JavaScript Within the Magento Framework
---

Exam proportion: (8%)

6.1  Include custom JavaScript on all pages

```xml
<default>
  <reference name="head">
    <!-- js/path/file.js -->
    <action method="addJs"><script>path/file.js</script></action>
    <!-- Or -->
    <!-- skin/frontend/package/theme/js/path/file.js -->
    <action method="addItem"><type>skin_js</type><name>js/path/file.js</name></action>
  </reference>
</default>
```

6.2 Include custom JavaScript on specific pages

```xml
<catalog_product_view>
  <reference name="head">
    <!-- js/path/file.js -->
    <action method="addJs"><script>path/file.js</script></action>
    <!-- Or -->
    <!-- skin/frontend/package/theme/js/path/file.js -->
    <action method="addItem"><type>skin_js</type><name>js/path/file.js</name></action>
  </reference>
</catalog_product_view>
```

6.3 Demonstrate understanding of using prototype.js

6.4 Override core JavaScript classes (without overriding core JavaScript files)

`addMethods() see prototype.js doc`

6.5 Configure JavaScript merging in the Admin panel

`System/configuration/Advanced (Developper)`

**Links :**
* [Prototype.js](http://prototypejs.org/learn/)
* [Prototype.js for jQuery Afficionados](https://blog.philwinkle.com/prototype-js-for-jquery-afficionados/)
* [Extending javascript methods Magento way](http://inchoo.net/magento/extending-javascript-methods-magento-way/)
* [JavaScript translations (translate.js)](http://bartosz-gorski.com/magento/magento-1-7-and-1-8-javascript-translations-translate-js/)

### 7. Use CSS Effectively to Customize Magento Look and Feel
---

Exam proportion: (9%)

7.1 CSS2

7.2 CSS Merging

`System/configuration/Advanced (Developper)`

7.3 CSS Compression

7.4 Other CSS skills

**Links :**
* [CSS Specificity: Things You Should Know](https://www.smashingmagazine.com/2007/07/css-specificity-things-you-should-know/)
* [15 Tips to Speed Up Your Website](https://moz.com/blog/15-tips-to-speed-up-your-website)
* [CSS Media Queries & Using Available Space](https://css-tricks.com/css-media-queries/)
* [Understanding Style Precedence in CSS: Specificity, Inheritance, and the Cascade](http://vanseodesign.com/css/css-specificity-inheritance-cascaade/)

### 8. Customize the Look and Feel of Specific Magento Pages
---

Exam proportion: (12%)




### 9. Correctly Use the Admin Configuration Scopes (Default/Website/Store View Fallback)
---

Exam proportion: (6%)

**Links :**
* [Configuration Scope](http://docs.magento.com/m1/ce/user_guide/configuration/scope.html)

### 10. Implement Internationalization of Frontend Pages (CE + EE)
---

Exam proportion: (4%)

10.1 Create and change translations

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;10.1.1 Understand the prioritization of translations methods

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  - Theme locale translate.csv file  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  - The database table core_translate

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;10.1.2 Understand the pros and the cons of applying translations via the translate.csv file versus the core_translate table

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;10.1.3 Understand how to apply a module scope to a translation

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;10.1.4 Understand the inline translation feature

10.2 Configure time zones and locale settings using the Admin panel

10.3 Configure currencies  

**Links :**
* [Internationalization](http://blog.belvg.com/magento-certified-developer-exam-internationalization.html)
* [Inline translation in Magento](http://inchoo.net/magento/inline-translation-in-magento/)
* [Manage Translation System in Magento](https://www.atwix.com/magento/manage-translation-system/)

## Study Guide Questions

[Magento Frontend Developer Certification Exam qa](http://www.demacmedia.com/magento-commerce/magento-frontend-developer-certification-exam-study-guide-qa/)

## Tests exemple questions

* [Magento Front End Developer - Test Questions](https://www.gitbook.com/book/robkent/magento-front-end-developer-test-questions/details)
* [Magento Front End Developer Mock Exam M70-301](http://www.webstructures.co.uk/magento-front-end-certification-mock-exam-m70-301/)

## Other ressources

* [Magento Front End Developer Certification Exam Study Techniques](http://www.demacmedia.com/magento-commerce/magento-front-end-developer-exam/)
* [Official Magento Design Guide](/common/pdf/MagentoDesignGuide.pdf)
* [Frontend Snippets](https://github.com/dannynimmo/magento-cheat-sheet)
