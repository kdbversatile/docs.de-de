---
title: 'Vorgehensweise: Entfernen von Elementen aus DomainUpDown-Steuerelementen in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DomainUpDown control [Windows Forms], removing items from
- spin button control [Windows Forms], removing items
ms.assetid: e70f5cbc-b497-41a9-975a-344c00e56ed2
ms.openlocfilehash: f56bc2b7b7b8a783ac298b220c83281f38da29da
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662351"
---
# <a name="how-to-remove-items-from-windows-forms-domainupdown-controls"></a>Vorgehensweise: Entfernen von Elementen aus DomainUpDown-Steuerelementen in Windows Forms
Entfernen von Elementen aus den Windows-Formularen <xref:System.Windows.Forms.DomainUpDown> Steuerelement durch Aufrufen der <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> oder <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> Methode der <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> Klasse. Die <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> -Methode entfernt ein bestimmtes Element, während die <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> Methode entfernt ein Element anhand seiner Position.  
  
### <a name="to-remove-an-item"></a>So entfernen Sie ein Element  
  
- Verwenden der <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> Methode der <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> Klasse, um ein Element anhand des Namens zu entfernen.  
  
    ```vb  
    DomainUpDown1.Items.Remove("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Remove("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Remove("noodles");  
    ```  
  
     - oder -   
  
- Verwenden der <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> Methode, um ein Element anhand seiner Position zu entfernen.  
  
    ```vb  
    ' Removes the first item in the list.  
    DomainUpDown1.Items.RemoveAt(0)  
    ```  
  
    ```csharp  
    // Removes the first item in the list.  
    domainUpDown1.Items.RemoveAt(0);  
    ```  
  
    ```cpp  
    // Removes the first item in the list.  
    domainUpDown1->Items->RemoveAt(0);  
    ```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DomainUpDown>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A?displayProperty=nameWithType>
- [DomainUpDown-Steuerelement](domainupdown-control-windows-forms.md)
- [Übersicht über das DomainUpDown-Steuerelement](domainupdown-control-overview-windows-forms.md)
