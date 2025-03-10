---
title: 对象和类
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic]
- objects [Visual Basic]
ms.assetid: c68c5752-1006-46e1-975a-6717b62a42fc
ms.openlocfilehash: d45aca8b137f56cf058b63b9286504259c0005eb
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346706"
---
# <a name="objects-and-classes-in-visual-basic"></a>Visual Basic 中的对象和类

*对象*结合了可以视为一个单元的代码和数据。 对象可以是应用程序的一部分（如控件或窗体）， 也可以是整个应用程序。

When you create an application in Visual Basic, you constantly work with objects. You can use objects provided by Visual Basic, such as controls, forms, and data access objects. You can also use objects from other applications within your Visual Basic application. 甚至可以创建你自己的对象，并为它们定义附加属性和方法。 对象类似于程序的预制构建基块，可方便你编写一次代码片段，然后不断重用它。

此主题详细介绍了对象。

## <a name="objects-and-classes"></a>对象和类

Each object in Visual Basic is defined by a *class*. 类描述了对象的变量、属性、过程和事件。 对象是类实例；定义类之后，便可以根据需要创建任意多个对象。

想想饼干切模和饼干，即可理解对象与其类之间的关系。 饼干切模是类。 它定义了每个饼干的特征，例如大小和形状。 类用于创建对象。 对象是饼干。

必须先创建对象，然后才能访问对象成员。

### <a name="to-create-an-object-from-a-class"></a>创建类对象的具体操作

1. 确定要创建哪个类的对象。

2. 编写 [Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)来创建一个变量，以便可以向其分配类实例。 变量应为相应类的类型。

   ```vb
   Dim nextCustomer As customer
   ```

3. 添加 [New 运算符](../../../../visual-basic/language-reference/operators/new-operator.md)关键字，将变量初始化为新的类实例。

   ```vb
   Dim nextCustomer As New customer
   ```

4. 现在可以通过对象变量访问类成员。

   ```vb
   nextCustomer.accountNumber = lastAccountNumber + 1
   ```

> [!NOTE]
> 应尽可能将变量声明为要向其分配的类类型。 这称为*早期绑定*。 如果在编译时不知道类类型，可将变量声明为 [Object 数据类型](../../../../visual-basic/language-reference/data-types/object-data-type.md)，从而调用晚期绑定。 不过，晚期绑定可能会降低性能，并限制对运行时对象成员的访问。 有关详细信息，请参阅[对象变量声明](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)。

### <a name="multiple-instances"></a>多个实例

新建的类对象通常彼此相同。 然而，作为单独对象后，便可以更改其变量和属性，与其他实例互不影响。 例如，如果向窗体添加三个复选框，那么每个复选框对象都是 <xref:System.Windows.Forms.CheckBox> 类的实例。 各个 <xref:System.Windows.Forms.CheckBox> 对象共用类定义的一组通用特征和功能（属性、变量、过程和事件）。 不过，每个对象都有自己的名称，不仅可以分开启用和禁用，还可以位于窗体上的不同位置。

## <a name="object-members"></a>对象成员

对象是应用程序元素，表示类*实例*。 字段、属性、方法和事件是对象的构建基块，构成了它的*成员*。

### <a name="member-access"></a>成员访问

按顺序指定对象变量的名称、句点 (`.`) 和成员名称即可访问对象的成员。 下面的示例设置 <xref:System.Windows.Forms.Label> 对象的 <xref:System.Windows.Forms.Control.Text%2A> 属性。

```vb
warningLabel.Text = "Data not saved"
```

#### <a name="intellisense-listing-of-members"></a>IntelliSense 列出成员

当你调用类的“列出成员”选项时（例如，将句点 (`.`) 作为成员访问运算符键入时），IntelliSense 会列出类的成员。 如果在声明为相应类实例的变量名称后键入句点，IntelliSense 会列出所有实例成员，而不列出任何共享成员。 如果在类名本身后面键入句点，IntelliSense 会列出所有共享成员，而不列出任何实例成员。 有关详细信息，请参阅[使用 IntelliSense](/visualstudio/ide/using-intellisense)。

### <a name="fields-and-properties"></a>字段和属性

*字段*和*属性*表示对象中存储的信息。 可以使用赋值语句检索和设置它们的值，方法与在过程中检索和设置局部变量的方法一样。 下面的示例检索 <xref:System.Windows.Forms.Control.Width%2A> 属性，并设置 <xref:System.Windows.Forms.Label> 对象的 <xref:System.Windows.Forms.Control.ForeColor%2A> 属性。

```vb
Dim warningWidth As Integer = warningLabel.Width
warningLabel.ForeColor = System.Drawing.Color.Red
```

请注意，字段亦称为“*成员变量*”。

在以下情况下，使用属性过程：

- 需要控制何时以及如何设置或检索值。

- 需要验证属性的一组明确定义的值。

- 设置值会导致对象状态发生某明显变化，如 `IsVisible` 属性。

- 设置属性会导致其他内部变量或其他属性的值发生变化。

- 必须先执行一系列步骤，然后才能设置或检索属性。

在以下情况下，使用字段：

- 值是自验证类型。 例如，如果将 `True` 或 `False` 之外的值赋给 `Boolean` 变量，则会发生错误或自动数据转换。

- 数据类型支持的范围中的任何值都有效。 对于 `Single` 或 `Double` 类型的许多属性，同样如此。

- 属性是 `String` 数据类型，并且对字符串的大小或值没有约束。

- 有关详细信息，请参阅[属性过程](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)。

### <a name="methods"></a>方法

“方法”是对象可以执行的操作。 例如，<xref:System.Windows.Forms.ComboBox.ObjectCollection.Add%2A> 是 <xref:System.Windows.Forms.ComboBox> 对象的方法，该对象将新条目添加到组合框。

下面的示例演示 <xref:System.Windows.Forms.Timer> 对象的 <xref:System.Windows.Forms.Timer.Start%2A> 用法。

```vb
Dim safetyTimer As New System.Windows.Forms.Timer
safetyTimer.Start()
```

请注意，方法只是对象公开的*过程*。

有关详细信息，请参阅[过程](../../../../visual-basic/programming-guide/language-features/procedures/index.md)。

### <a name="events"></a>事件

事件是由对象识别的操作（如单击鼠标或按某个键），可以编写代码来响应这些操作。 事件可能是由用户操作或程序代码生成，也可能是由系统生成。 提示事件发生的代码可以说是负责*引发*事件，而响应事件的代码则可以说是负责*处理*事件。

还可以开发你自己的自定义事件，以便由对象引发并由其他对象处理。 有关详细信息，请参阅[事件](../../../../visual-basic/programming-guide/language-features/events/index.md)。

### <a name="instance-members-and-shared-members"></a>实例成员和共享成员

创建类对象时，生成的是相应类实例。 未使用 [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) 关键字声明的成员是*实例成员*，严格属于特定实例。 一个实例中的实例成员与同一类的另一实例中的同一成员互不影响。 例如，一个实例成员变量可以在不同的实例中有不同的值。

使用 `Shared` 关键字声明的成员是*共享成员*，属于整个类，而不属于任何特定实例。 无论创建多少类实例，或者即便未创建实例，共享成员也都只有一个。 例如，共享成员变量只有一个值，可供访问相应类的所有代码使用。

#### <a name="accessing-nonshared-members"></a>访问非共享成员

##### <a name="to-access-a-nonshared-member-of-an-object"></a>访问对象的非共享成员的具体操作

1. 请确保已创建类对象，并已将对象分配给对象变量。

   ```vb
   Dim secondForm As New System.Windows.Forms.Form
   ```

2. 在访问成员的语句中，对象变量名称后面依次是*成员访问运算符* (`.`) 和成员名称。

   ```vb
   secondForm.Show()
   ```

#### <a name="accessing-shared-members"></a>访问共享成员

##### <a name="to-access-a-shared-member-of-an-object"></a>访问对象的共享成员的具体操作

- 类名后面依次是*成员访问运算符* (`.`) 和成员名称。 应始终通过类名直接访问对象的 `Shared` 成员。

   ```vb
   MsgBox("This computer is called " & Environment.MachineName)
   ```

- 如果已创建了类对象，也可以通过对象的变量访问 `Shared` 成员。

### <a name="differences-between-classes-and-modules"></a>类和模块的区别

类和模块的主要区别是，类可以实例化成对象，而标准模块则不能。 因为只有一个标准模块数据副本，所以当程序的一部分更改标准模块中的公共变量时，如果程序的其他任何部分读取了此变量，也会获得相同的值。 相反，每个实例化的对象都有各自的对象数据。 还有一个区别是，与标准模块不同，类可以实现接口。

> [!NOTE]
> 将 `Shared` 修饰符应用于类成员时，它是与类本身相关联，而不是与特定的类实例相关联。 类成员是使用类名直接访问，方法与访问模块成员一样。

此外，类和模块对其成员划定的范围也不同。 类中定义的成员将范围限定为类的特定实例内，并且仅存在于对象的生存期内。 若要从类外部访问类成员，必须使用 *Object*.*Member* 格式的完全限定的名称。

相比之下，在模块中声明的成员默认可公开访问，并且可由能够访问模块的任意代码进行访问。 也就是说，标准模块中的变量实际上是全局变量，因为它们在项目的任何位置都可见，并且存在于程序的生存期内。

## <a name="reusing-classes-and-objects"></a>重用类和对象

使用对象，只需声明变量和过程一次，即可根据需要随时重用它们。 例如，如果要向应用程序添加拼写检查，可以定义所有变量和支持函数，以提供拼写检查功能。 如果将拼写检查创建为类，可以添加对已编译程序集的引用，从而在其他应用程序中重用此类。 更好的是，可以使用别人已经开发的拼写检查类，从而减少自己的工作量。

The .NET Framework provides many examples of components that are available for use. 下面的示例使用 <xref:System> 命名空间中的 <xref:System.TimeZone> 类。 <xref:System.TimeZone> 提供的成员可检索当前计算机系统的时区信息。

```vb
Public Sub examineTimeZone()
    Dim tz As System.TimeZone = System.TimeZone.CurrentTimeZone
    Dim s As String = "Current time zone is "
    s &= CStr(tz.GetUtcOffset(Now).Hours) & " hours and "
    s &= CStr(tz.GetUtcOffset(Now).Minutes) & " minutes "
    s &= "different from UTC (coordinated universal time)"
    s &= vbCrLf & "and is currently "
    If tz.IsDaylightSavingTime(Now) = False Then s &= "not "
    s &= "on ""summer time""."
    MsgBox(s)
End Sub
```

在上面的示例中，第一个 [Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)声明 <xref:System.TimeZone> 类型的对象变量，并将其分配到由 <xref:System.TimeZone.CurrentTimeZone%2A> 属性返回的 <xref:System.TimeZone> 对象。

## <a name="relationships-among-objects"></a>对象之间的关系

对象可通过多种方式彼此关联。 两种主要关系是*分层*和*包含*关系。

### <a name="hierarchical-relationship"></a>分层关系

如果类派生自更为基础的类，可以认为构成了*分层关系*。 当描述更为通用的类的子类型项时，类层次结构就很有用。

在下面的示例中，假设要定义一种特殊类型的 <xref:System.Windows.Forms.Button>，类似于普通的 <xref:System.Windows.Forms.Button>，不同之处在于公开了用于保留前景色和背景色的方法。

#### <a name="to-define-a-class-is-derived-from-an-already-existing-class"></a>定义派生自现有类的类的具体操作

1. 使用 [Class 语句](../../../../visual-basic/language-reference/statements/class-statement.md)定义要创建其所需对象的类。

   ```vb
   Public Class reversibleButton
   ```

   请务必在类的最后一行代码后添加 `End Class` 语句。 默认情况下，集成开发环境 (IDE) 会在你输入 `Class` 语句时自动生成 `End Class`。

2. 在 `Class` 语句后面紧接着编写 [Inherits 语句](../../../../visual-basic/language-reference/statements/inherits-statement.md)。 指定新类派生自的类。

   ```vb
   Inherits System.Windows.Forms.Button
   ```

   新类继承了基类定义的所有成员。

3. 添加派生类公开的其他成员的代码。 例如，可以添加 `reverseColors` 方法，派生类将如下所示：

   ```vb
   Public Class reversibleButton
       Inherits System.Windows.Forms.Button
           Public Sub reverseColors()
               Dim saveColor As System.Drawing.Color = Me.BackColor
               Me.BackColor = Me.ForeColor
               Me.ForeColor = saveColor
          End Sub
   End Class
   ```

   如果从 `reversibleButton` 类创建对象，它可以访问 <xref:System.Windows.Forms.Button> 类的所有成员，以及你在 `reversibleButton` 上定义的 `reverseColors` 方法和其他任何新成员。

派生类继承基类的成员，因此随着类层次结构的不断深入，复杂性也随之增加。 有关详细信息，请参阅[继承基础知识](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)。

### <a name="compiling-the-code"></a>编译代码

请确保编译器可以访问要从中派生新类的类。 也就是说，完全限定其名称（如上面的示例所示），或在 [Imports 语句（.NET 命名空间和类型）](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)中标识其命名空间。 如果类在不同的项目中，可能需要添加对相应项目的引用。 有关详细信息，请参阅[管理项目中的引用](/visualstudio/ide/managing-references-in-a-project)。

### <a name="containment-relationship"></a>包含关系

另一种对象关联方式是使用*包含关系*。 容器对象在逻辑上封装其他对象。 例如，<xref:System.OperatingSystem> 对象在逻辑上包含一个通过其 <xref:System.OperatingSystem.Version%2A> 属性返回的 <xref:System.Version> 对象。 请注意，容器对象实际上并不包含其他任何对象。

#### <a name="collections"></a>集合

一种特殊类型的对象包含关系用*集合*来表示。 集合是一组可以枚举的类似对象。 Visual Basic supports a specific syntax in the [For Each...Next Statement](../../../../visual-basic/language-reference/statements/for-each-next-statement.md) that allows you to iterate through the items of a collection. 此外，借助集合，通常还可以使用 <xref:Microsoft.VisualBasic.Collection.Item%2A> 根据索引检索元素，或通过将元素与唯一字符串相关联进行检索。 集合比数组更易于使用，因为无需使用索引，即可添加或删除项。 鉴于它的易用性，集合通常用于存储窗体和控件。

## <a name="related-topics"></a>相关主题

[Walkthrough: Defining Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/walkthrough-defining-classes.md)\
分步说明了如何创建类。

[Overloaded Properties and Methods](../../../../visual-basic/programming-guide/language-features/objects-and-classes/overloaded-properties-and-methods.md)\
重载属性和方法

[继承的基础知识](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)\
介绍了继承修饰符、重写方法和属性（MyClass 和 MyBase）。

[对象生存期：如何创建和销毁对象](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)\
介绍了如何创建和释放类实例。

[匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)\
介绍了如何创建和使用匿名类型，这样无需为数据类型编写类定义即可创建对象。

[对象初始值设定项：命名类型和匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)\
介绍了对象初始值设定项，用于通过一个表达式创建已命名和匿名类型的实例。

[How to: Infer Property Names and Types in Anonymous Type Declarations](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)\
介绍了如何推断匿名类型声明中的属性名称和类型。 收录了推理成功和失败的示例。
