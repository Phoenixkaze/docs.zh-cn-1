---
title: Private
ms.date: 07/20/2015
f1_keywords:
- vb.Private
helpviewer_keywords:
- Private keyword [Visual Basic]
- Private keyword [Visual Basic], syntax
ms.assetid: aba74a2e-5824-4613-bf63-b9ec7787f4e6
ms.openlocfilehash: 5600744aeca79a54f51a1f9ecd0ef00fed4b00fd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351333"
---
# <a name="private-visual-basic"></a>Private (Visual Basic)
Specifies that one or more declared programming elements are accessible only from within their declaration context, including from within any contained types.  
  
## <a name="remarks"></a>备注  
 If a programming element represents proprietary functionality, or contains confidential data, you usually want to limit access to it as strictly as possible. You achieve the maximum limitation by allowing only the module, class, or structure that defines it to access it. To limit access to an element in this way, you can declare it with `Private`.  

> [!NOTE]
> You can also use the [Private Protected](private-protected.md) access modifier, which makes a member accessible from within that class and from derived classes located in its containing assembly.

## <a name="rules"></a>规则  

- **Declaration Context.** 只能在模块级别使用 `Private`。 This means the declaration context for a `Private` element must be a module, class, or structure, and cannot be a source file, namespace, interface, or procedure.  
  
## <a name="behavior"></a>行为  
  
- **Access Level.** All code within a declaration context can access its `Private` elements. This includes code within a contained type, such as a nested class or an assignment expression in an enumeration. No code outside of the declaration context can access its `Private` elements.  
  
- **Access Modifiers.** The keywords that specify access level are called *access modifiers*. For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 `Private` 修饰符可用于下面的上下文中：  
  
 [Class 语句](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Const 语句](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [Declare 语句](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Delegate 语句](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Enum 语句](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Interface 语句](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Structure 语句](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>请参阅

- [COMClassAttribute](../../../visual-basic/language-reference/modifiers/public.md)
- [Protected](../../../visual-basic/language-reference/modifiers/protected.md)
- [Friend](../../../visual-basic/language-reference/modifiers/friend.md)
- [Private Protected](./private-protected.md)
- [Protected Friend](./protected-friend.md)    [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [过程](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [结构](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [对象和类](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
