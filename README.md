
# Rule 规则  

+ [ARIA: Row Role](#aria-row-roletop)

+ [ARIA: Rowgroup Role](#aria-rowgroup-roletop)

+ [ARIA: Search Role](#aria-search-role)

+ [ARIA: Switch Role](#aria-switch-role)

+ [ARIA: Table Role](#aria-table-role)

+ [ARIA: Tabpanel Role](#aria-tabpanel-role)

+ [ARIA: Textbox Role](#aria-textbox-role)

+ [ARIA: Timer Role](#aria-timer-role)

****

## Aria: Row Role<sup>[Top](#rule-规则)</sup>

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

## Aria: Rowgroup Role<sup>[Top](#rule-规则)</sup>  

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

## ARIA: search role

search [landmark]角色用于标识用于搜索页面、站点或站点集合的页面部分。

```html
<form role="search">
  <!-- search input -->
</form>
```

### 多余的描述

屏幕阅读器会宣布这个地标的角色类型。因此，您不需要在其标签中描述地标是什么。例如，带有aria-label="Sitewide search"的`role="search"`声明可以冗余地声明为"Sitewide search search"。

## ARIA: switch role

ARIA `switch`角色在功能上与checkbox角色完全相同，只是`switch`角色不表示"checked"和"unchecked"状态，这两个状态在意义上相当通用，而是表示"on"和"off"状态

本例创建一个小部件并为其分配ARIA `switch`角色。

```HTML
<button type="button" role="switch" aria-checked="true"
    id="speakerPower" class="switch">
    <span>off</span>
    <span>on</span>
</button>
<label for="speakerPower" class="switch">Speaker power</label>
```

ARIA `switch`角色与checkbox角色相同，除了不是"checked"或"unchecked"，而是"on"和"off"。与checkbox角色一样，`aria-checked`属性是必需的。两个可能的值是`true`和`false`。与`<checkbox>`或role="checkbox"不同，没有不确定或混合状态。switch角色不支持`aria-checked`属性的值`mixed`；为开关分配`mixed`值反而会将该值设置为`false`。

辅助技术可以选择用专门的表示来表示开关部件，以反映开关的概念。

由于`swich`是一个交互式控件，它必须是可调焦的，并且可以使用键盘。如果角色应用于不可聚焦的元素，请使用tabindex属性来更改它。切换开关值所需的键盘快捷键是<kbd>space</kbd>空格键。切换开关时，开发人员需要动态更改`aria-checked`属性的值。

## ARIA: tab role

ARIA `tab`角色表示tablist中的一个交互元素，激活该元素后，将显示其关联的tabpanel。

```HTML
<button role="tab" aria-selected="true" aria-controls="tabpanel-id" id="tab-id">Tab label</button>
```

### 说明

具有`tab`角色的元素控制具有`tabpane`l角色的关联元素的可见性。常见的用户体验模式是内容区域上方或侧面的一组可视选项卡，选择不同的选项卡会更改内容并使所选选项卡比其他选项卡更突出。

具有`tab`选项卡的元素必须是具有`tablist`角色的元素的子元素，或者具有`tablist`的id部分拥有`aria-owns`的属性。这种组合向辅助技术标识元素是一组相关元素的一部分。一些辅助技术将提供一个`tablist`中`tab`角色元素的数量，并通知用户他们当前的目标选项卡。它们应该包含aria控件属性，标识具有`tabpanel`角色的元素。当具有`tabpane`l角色的元素具有焦点或其子元素具有焦点时，这表示具有tab角色的连接元素是表列表中的活动选项卡。

当处理具有`tab`角色的元素时，当它们被选中或处于活动状态时，它们的`aria-selecte`d属性应该设置为`true`，否则应该设置为`false`。当一个选项卡被选中或处于活动状态时，其受控的`tabpanel`应将其aria展开并将隐藏属性设置为`true`，否则应将其设置为`false`。

## ARIA: table role

ARIA role属性的`table`值将包含角色的元素标识为具有非交互式表结构，该结构包含按行和列排列的数据，类似于原生的<table>HTML元素。

```HTML
<div role="table" aria-label="Semantic Elements" aria-describedby="semantic_elements_table_desc" aria-rowcount="81">
  <div id="semantic_elements_table_desc">Semantic Elements to use instead of ARIA's roles</div>
  <div role="rowgroup">
    <div role="row">
      <span role="columnheader" aria-sort="none">ARIA Role</span>
      <span role="columnheader" aria-sort="none">Semantic Element</span>
    </div>
  </div>
  <div role="rowgroup">
    <div role="row" aria-rowindex="11">
      <span role="cell">header</span>
      <span role="cell">h1</span>
    </div>
    <div role="row" aria-rowindex="16">
      <span role="cell">header</span>
      <span role="cell">h6</span>
    </div>
    <div role="row" aria-rowindex="18">
      <span role="cell">rowgroup</span>
      <span role="cell">thead</span>
    </div>
    <div role="row" aria-rowindex="24">
      <span role="cell">term</span>
      <span role="cell">dt</span>
    </div>
  </div>
</div>
```

### 说明

带有role=“table”的元素是一个静态表格结构，其中的行包含单元格。单元格不可对焦或不可选择，尽管表中单个单元格中的小部件可以交互。强烈建议尽可能使用本机HTML表元素。

> *注意*: 如果表保持选择状态，具有二维导航，或允许用户重新排列单元格顺序，请改用`grid`或`treegrid`。

要创建ARIA表，请将`role="table"`添加到容器元素中。在该容器中，每一行都设置了role="row"并包含子单元格。每个单元格都有一个角色`columnheader`、`rowheader`或简单的`cell`。行可以是表的子行，也可以是行组中的子行。

表标题可以通过aria-labelledby或aria-label定义。所有其他语义表元素，如`<tbody>`、`<thead>`、`<tr>`、`<th>`和`<td>`都需要通过相关联的角色（如rowgroup、row、columnheader和cell）添加。

如果表包含可排序的列或行，则应在头单元格元素（而不是表本身）上添加`aria-sort`属性。如果任何行或列被隐藏，则应包括`aria-colcount`或`aria-rowcount`，分别指示列或行的总数，以及每个单元格上的`aria-colindex`或`aria-rowindex`。`aria-colindex`或`aria-rowindex`分别设置为行或列中单元格的位置。如果表包含跨多行或多列的单元格，则还应包括`aria-rowspan`或`aria-colspan`。要知道，简单地使用<`table>`元素以及所有相关的语义元素和属性（所有辅助技术都支持这些元素和属性）要简单得多。

要创建具有表格结构的交互式小部件，请改用网格模式。如果交互提供了单个单元的选择状态，如果提供了从左到右和从上到下的导航，或者如果用户界面允许重新排列单元顺序或通过拖放等方式更改单个单元的顺序，请改用grid或treegrid。

## ARIA: tabpanel role

待官方文档补充

## ARIA: textbox role

`textbox`角色用于标识允许输入自由格式文本的元素。只要可能，不要使用此角色，对于单行输入使用带有type="text"的·元素，或者对于多行输入使用·元素。

### 说明

当元素具有textbox角色时，浏览器将向assistive technologies发送一个可访问的textbox事件，然后assistive technologies可以通知用户该事件。

默认值是单行输入，其中<kbd>Return</kbd>或<kbd>Enter</kbd>提交表单；在这种情况下，最好使用带有`type="text"`的HTML`<input>`。要创建支持换行符的多行文本框，如在HTML`<textarea>`中，请设置aria `multiline="true"`。包含HTML`contenteditable`属性可确保文本节点是可编辑的。

```HTML
<!-- Simple text input field -->
<div id="txtboxLabel">Enter your five-digit zipcode</div>
<div role="textbox" contenteditable="true" aria-placeholder="5-digit zipcode" aria-labelledby="txtboxLabel"></div>

<!-- Multi-line text area -->
<div id="txtboxMultilineLabel">Enter the tags for the article</div>
<div role="textbox" contenteditable="true" aria-multiline="true"
   aria-labelledby="txtboxMultilineLabel" aria-required="true"></div>

<label for="txtbox">Enter your five-digit zipcode</label>
<input type="text" placeholder="5-digit zipcode" id="txtbox"/>

<!-- Multi-line text area -->
<label for="txtboxMultiline">Enter the tags for the article</label>
<textarea id="txtboxMultiline" required></textarea>
```

### 关联的ARIA属性

`aria-activesubcent`属性

作为它的值，ID要么是具有DOM焦点的元素的后代，要么是aria owns属性所指示的逻辑后代，它指示该元素何时具有焦点，何时是组合框等组合小部件的一部分。例如，在组合框中，焦点可能会保持在textbox上，而textbox元素上的aria activedescendant的值引用由控制的弹出列表框的子体文本框。这个属性必须在焦点更改时以编程方式更新。

`aria-autocomplete` 自动完成属性

指示用户对字段的输入是否以及如何触发对预期值的预测的显示。它支持以下值：

+ `inline`：在插入符号后插入预测文本。

+ `list`：预测文本以值集合的形式显示。

+ `both`：预测文本以值集合的形式呈现，文本需要完成插入符号后的一个值。

+ `none`（默认值）：未提供文本。

如果设置了list或两者，则还应包括`aria-controls`和`aria -haspopup`属性。`aria-controls`的值是包含建议值列表的元素的ID。此外，无论是文本框还是包含角色`"combobox"`的元素都具有`aria-haspopup`的值，该值与包含建议值列表的元素的角色相匹配。

`aria-multiline` 多行属性

如果设置了`aria-multiline="true"`，AT会通知用户文本框支持多行输入，并期望<kbd>Enter</kbd>或<kbd>Return</kbd>将创建一个换行符，而不是提交表单。ARIA不会改变元素的行为；相反，这个特性必须由开发人员控制。如果设置了`false`，或者省略了属性并默认为`false`，那么用户期望控件是一个单行文本框，<kbd>Enter</kbd>或<kbd>Return</kbd>会提交表单。

`aria-placeholder` 占位符属性

表示向用户提示要在文本字段中输入的内容。提示应该是示例值或对预期的格式。这个信息不应被用作标签的替代品：标签是可聚焦的、永久的，它指示了预期的信息类型，并增加了设置控件焦点的影响范围，而占位符文本只是关于预期值的临时提示，如果实现不正确，可能会降低可访问性。当控件的值为空字符串时（例如控件首次接收焦点时以及用户删除以前输入的值时），占位符应可见。不要使用`aria-placeholder`，而是使用带有占位符属性的语义<`input type="text">`或`<textarea>`。

`aria-readonly` 只读属性

指示用户无法修改文本字段的值。不要使用aria readonly，而是使用带有`readonly`属性的语义`<input type="text">`或`<textarea>`。

`aria-required` 必需属性

指示在提交字段之前必须为其提供值。不要使用`aria-required`，而是使用语义`<input type="text">`或带有必需属性的`<textarea>`。

## ARIA: timer role

`timer`角色向assistive technologies指示元素是一个数字计数器，列出从起始点到结束点所用的时间或剩余时间。

```HTML
<div role="timer" id="eggtimer">0</div>
```
它将这个div元素定义为没有剩余时间的计时器。
****

[ARIA]:  https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/Row_Role  
[landmark]:  https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques#Landmark_roles
