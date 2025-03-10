---
title: 枚举类型 - C# 编程指南
ms.custom: seodec18
ms.date: 09/10/2017
helpviewer_keywords:
- enumerations [C#]
- enums [C#]
- C# Language, enums
- bit flags [C#]
ms.assetid: 64a9b731-9e3c-4336-8a09-018db2aa10b7
ms.openlocfilehash: 3573959a1e10b475a9867631767de5d10a08b9ea
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2019
ms.locfileid: "73969764"
---
# <a name="enumeration-types-c-programming-guide"></a>枚举类型（C# 编程指南）

枚举类型（也称为枚举）提供了一种有效的方式来定义可能分配给变量的一组已命名整数常量。 例如，假设你需要定义一个变量，其值表示一周内的某一天。 该变量只会存储七个有意义的值。 若要定义这些值，可以使用枚举类型，该类型是使用 [enum](../language-reference/keywords/enum.md) 关键字声明的。

[!code-csharp[csProgGuideEnums#1](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#1)]

默认情况下，枚举中每个元素的基础类型都为 [int](../language-reference/builtin-types/integral-numeric-types.md)。可以使用冒号指定另一种整数类型，如上例所示。 有关可能的类型的完整列表，请参阅 [enum（C# 参考）](../language-reference/keywords/enum.md)。

可以通过转换为基础类型来验证基础数值，如下例所示。

```csharp
Day today = Day.Monday;
int dayNumber =(int)today;
Console.WriteLine("{0} is day number #{1}.", today, dayNumber);

Month thisMonth = Month.Dec;
byte monthNumber = (byte)thisMonth;
Console.WriteLine("{0} is month number #{1}.", thisMonth, monthNumber);

// Output:
// Monday is day number #1.
// Dec is month number #11.
```

以下是使用枚举而不使用数值类型的好处：

- 明确为客户端代码指定对变量有效的值。

- 在 Visual Studio 中，IntelliSense 列出了定义的值。

如果未为枚举器列表中的元素指定值，则值将自动按 1 递增。 在上例中，`Day.Sunday` 的值为 0，`Day.Monday` 的值为 1，依此类推。 创建新的 `Day` 对象时，如果没有明确为其分配值，它将具有默认值 `Day.Sunday` (0)。 创建枚举时，请选择最有逻辑的默认值，并为其分配值零。 这将导致所有枚举都具有默认值（如果未在创建时显式分配值）。

如果变量 `meetingDay` 的类型为 `Day`，那么在没有显式转换的情况下只能为其分配由 `Day` 定义的值。 如果会议日期更改，可以将 `Day` 中的新值分配给 `meetingDay`：

[!code-csharp[csProgGuideEnums#4](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#4)]

> [!NOTE]
> 可以将任意整数值分配给 `meetingDay`。 例如，代码行 `meetingDay = (Day) 42` 不会产生错误。 但应避免这样做，因为隐式预期是枚举变量只会持有枚举所定义的其中一个值。 为枚举类型的变量分配任意值很可能会引发错误。

可以为枚举类型的枚举器列表中的元素分配任何值，也可以使用计算值：

[!code-csharp[csProgGuideEnums#3](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#3)]

## <a name="enumeration-types-as-bit-flags"></a>作为位标志的枚举类型

可以使用枚举类型来定义位标志，这使枚举类型的实例能够存储枚举器列表中定义的值的任何组合。 （当然，某些组合在你的程序代码中可能没有意义或不允许使用。）

创建位标志枚举的方法是，应用 <xref:System.FlagsAttribute?displayProperty=nameWithType> 属性并适当定义一些值，以便可以对这些值执行 `AND`、`OR`、`NOT` 和 `XOR` 按位运算。 在位标志枚举中，包括一个值为零（表示“未设置任何标志”）的命名常量。 如果零值不表示“未设置任何标志”，请勿为标志指定零值。

在以下示例中，定义了名为 `Days` 枚举的另一个版本，命名为 `Day`。 `Days` 具有 `Flags` 属性，且它的每个值都是 2 的若干次幂，指数依次递增。 这样，你就能够创建值为 `Days.Tuesday | Days.Thursday` 的 `Days` 变量。

[!code-csharp[csProgGuideEnums#2](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#2)]

若要在枚举上设置标志，请使用按位 `OR` 运算符，如以下示例所示：

[!code-csharp[csProgGuideEnums#6](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#6)]

若要确定是否设置了特定标志，请使用按位 `AND` 运算，如以下示例所示：

[!code-csharp[csProgGuideEnums#7](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#7)]

有关使用 <xref:System.FlagsAttribute?displayProperty=nameWithType> 特性定义枚举类型时应考虑事项的详细信息，请参阅 <xref:System.Enum?displayProperty=nameWithType>。

## <a name="using-the-systemenum-methods-to-discover-and-manipulate-enum-values"></a>使用 System.Enum 方法来发现和操作枚举值

所有枚举都是 <xref:System.Enum?displayProperty=nameWithType> 类型的实例。 不能从 <xref:System.Enum?displayProperty=nameWithType> 中派生新类，但可以使用它的方法来发现有关枚举实例中操作值的信息。

[!code-csharp[csProgGuideEnums#5](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#5)]

有关详细信息，请参阅 <xref:System.Enum?displayProperty=nameWithType>。

还可以使用扩展方法创建枚举的新方法。 有关详细信息，请参阅[如何为枚举创建新方法](./classes-and-structs/how-to-create-a-new-method-for-an-enumeration.md)。

## <a name="see-also"></a>请参阅

- <xref:System.Enum?displayProperty=nameWithType>
- [C# 编程指南](./index.md)
- [enum](../language-reference/keywords/enum.md)
