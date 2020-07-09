
# Rule 规则  

+ [ARIA: Row Role](#aria-row-role)

+ [ARIA: Rowgroup Role](#rowgroup-role)

+ [ARIA: Search Role](#search-role)

+ [ARIA: Switch Role](#switch-role)

+ [ARIA: Table Role](#table-role)

+ [ARIA: Tabpanel Role](#tabpanel-role)

+ [ARIA: Textbox Role](#textbox-role)

+ [ARIA: Timer Role](#timer-role)

****

## Aria: Row Role

具有`role='row'`的元素是表格结构中的一行单元格。一行包含一个或多个单元格、网格单元格或列标题，还可能包含一个行标题，位于网格、表或树表中，也可以在行组中包含。出自[ARIA]

### **代码块**  

``` HTML  

<div role="table" aria-label="Populations" aria-describedby="country_population_desc">
    <div id="country_population_desc">World Populations by Country</div>
    <div role="rowgroup">
        <div role="row">
            <span role="columnheader" aria-sort="descending">Country</span>
            <span role="columnheader"aria-sort="none">Population</span>
        </div>
    </div>
    <div role="rowgroup">
        <div role="row">
        <span role="cell">Finland</span>
        <span role="cell">5.5 million</span>
        </div>
        <div role="row">
        <span role="cell">France</span>
        <span role="cell">67 million</span>
        </div>
    </div>
</div>
```

### **上下文角色**

`role="rowgroup"`

+ 作为可选的上下文行父级，它在子行之间建立关系。它在结构上等价于HTML表元素中的thead、tfoot和tbody元素。

`role="table"`

+ 三种可能的上下文之一（以及grid和treegrid）中的一种，它将该行标识为非交互式表结构的一部分，该结构包含按行和列排列的数据，类似于原生的`<table>`HTML元素。

`role="grid"`

+ 三种可能的上下文之一（以及table和treegrid），它将该行标识为非交互式表结构的一部分，该结构包含按行和列排列的数据，类似于原生的`<table>`HTML元素。

`role="treegrid"`

+ 类似于网格，但其行可以以与树相同的方式展开和折叠。

### **后代角色**

`role="cell"`

+ 表格容器中一行中的单元格。

`role="gridcell"`

+ 网格或树状结构中一行的单元。

`role="columnheader"`

+ 与具有列范围的HTML`<th>`元素的结构等效的标题单元格。与普通单元格不同，columnheader角色在它与相应列中的所有单元格之间建立关系。

`role="rowheader"`

+ 与具有行范围的HTML`<th>`元素的结构等效的标题单元格。与普通单元格不同，rowheader角色在它与相应行中的所有单元格之间建立关系。

### 状态和属性

`aria-expanded` 扩展状态

+ 定义行状态的`aria expanded`属性可以采用以下三个值之一，也可以省略：

  + `aria expanded="true"`:行当前已展开。

  + `aria expanded="false"`：行当前已折叠。

  + `aria expanded="undefined"`或缺少属性：行既不可展开也不可折叠。

+ 如果具有`aria expanded`属性的元素控制另一个分组容器的扩展，而该容器不是由该元素“拥有”的，则作者**应该**使用aria controls属性引用该容器。

`aria-selected` 选定状态

+ 仅当行位于交互式容器（如网格或treegrid）中时相关，但如果行在表中则不相关。aria selected属性可以采用以下三个值之一，也可以省略：

  + `aria selected="true"`:当前已选定行

  + `aria selected="false"`：当前未选择行。

  + `aria selected="undefined”`或缺少属性：该行不可选择。

`aria-colindex` 属性

+ 只有在对DOM隐藏列时才需要`aria-colindex`属性。它通常放在row子元素上，而不是row本身。如果显示的列是连续的，则可以将其放置在行上。

+ 该属性的值为1和表、网格或treegrid中列总数之间的整数。当放在行上时，`aria-colindex`定义元素的列索引或相对于行中列总数的位置。例如，在一个有15列的表中，第4、5和6列在DOM中，可以在每一行上设置`aria colindex="4"`。

+ 如果DOM中出现的列集不是连续的，或者有跨越多个行或列的单元格，则将`aria-colindex`放在每行的所有子级上，而不是放在行本身上。

+ 如果所有列都在DOM中，则不需要该属性。

`aria-rowindex`属性

+ 只有在对DOM隐藏行时，才需要`aria-rowindex`属性，以指示正在读取总行列表中的哪一行。该属性在每一行上都有一个唯一的值，它的值是一个介于1和表、网格或treegrid中的总行数之间的整数，表示每行的位置或索引。例如，如果一个表有1500行，但在DOM中只有标题和第47行和第52行，则在标题行上设置`aria-rowindex="1"`，在第47行和第52行分别设置`aria- rowindex="47"`和`aria-rowindex="52"`。

+ 如果所有行都存在于DOM中，则不需要该属性。

****

## Rowgroup Role  

具有`role="rowgroup"`的元素是表格结构中的一组行。行组包含一行或多行单元格、网格单元格、列标题或网格、表或树表中的行标题。  

### 上下文角色

`role="table"`

+ 三种可能的上下文之一（以及grid和treegrid），您可以在其中找到一行。将表中的`<row>`元素标识为非交互式结构的`<row>`部分。

`role="grid"`

+ 三种可能的上下文之一（以及table和treegrid），您可以在其中找到一行。将表中的`<row>`元素标识为非交互式结构的`<row>`部分。

`role="treegrid"`

+ 类似于网格，但其行可以以与树相同的方式展开和折叠。

### 后代角色

`role="row"`

+ 表格结构中的一行单元格。行包含一个或多个单元格、gridcell或列标题，有时还包含行标题。

[ARIA]:  https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/Row_Role
