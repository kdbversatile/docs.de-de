---
title: 'Gewusst wie: Definieren eines Parameters für eine Prozedur'
ms.date: 07/20/2015
helpviewer_keywords:
- procedure parameters [Visual Basic], defining data types for
- procedures [Visual Basic], parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters [Visual Basic], defining
ms.assetid: 7962808d-407e-4e84-984e-43e9857c53c9
ms.openlocfilehash: 411959a7be92ea49a59558b508e992bfba8eff95
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344886"
---
# <a name="how-to-define-a-parameter-for-a-procedure-visual-basic"></a>Gewusst wie: Definieren eines Parameters für eine Prozedur (Visual Basic)
Ein *Parameter* ermöglicht es dem aufrufenden Code, einen Wert an die Prozedur zu übergeben, wenn er aufgerufen wird. Sie deklarieren jeden Parameter für eine Prozedur auf dieselbe Weise, wie Sie eine Variable deklarieren, indem Sie Ihren Namen und den Datentyp angeben. Außerdem geben Sie den Übergabe Mechanismus an und gibt an, ob der Parameter optional ist.  
  
 Weitere Informationen finden Sie unter [Prozedur Parameter und-Argumente](./procedure-parameters-and-arguments.md).  
  
### <a name="to-define-a-procedure-parameter"></a>So definieren Sie einen Prozedur Parameter  
  
1. Fügen Sie in der Prozedur Deklaration den Parameternamen der Parameterliste der Prozedur hinzu, und trennen Sie ihn von anderen Parametern durch Kommas.  
  
2. Entscheiden Sie sich für den Datentyp des Parameters.  
  
3. Befolgen Sie den Parameternamen mit einer `As`-Klausel, um den Datentyp anzugeben.  
  
4. Entscheiden Sie sich für den für den Parameter gewünschten Übergabe Mechanismus. Normalerweise übergeben Sie einen Parameter nach Wert, es sei denn, Sie möchten, dass die Prozedur ihren Wert im aufrufenden Code ändern kann.  
  
5. Stellen Sie dem Parameternamen " [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) " oder " [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) " voran, um den Übergabe Mechanismus anzugeben. Weitere Informationen finden Sie [unter Unterschiede zwischen dem übergeben von Argumenten als Wert und als Verweis](./differences-between-passing-an-argument-by-value-and-by-reference.md).  
  
6. Wenn der Parameter optional ist, stellen Sie dem Übergabe Mechanismus [optional](../../../../visual-basic/language-reference/modifiers/optional.md) einen Wert vor, und befolgen Sie den Parameter Datentyp mit einem Gleichheitszeichen (`=`) und einem Standardwert.  
  
     Im folgenden Beispiel wird die Gliederung einer `Sub` Prozedur mit drei Parametern definiert. Die ersten beiden sind erforderlich, und die dritte ist optional. Die Parameter Deklarationen werden durch Kommas in der Parameterliste getrennt.  
  
     [!code-vb[VbVbcnProcedures#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#33)]  
  
     Der erste Parameter akzeptiert ein `customer` Objekt, und `updateCustomer` kann die an `c` übergebenen Variable direkt aktualisieren, da das Argument [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)übergeben wird. Die-Prozedur kann die Werte der letzten beiden Argumente nicht ändern, da Sie [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)übermittelt werden.  
  
     Wenn der Aufruf Code keinen Wert für den `level`-Parameter bereitstellt, legt Visual Basic ihn auf den Standardwert 0 fest.  
  
     Wenn der Schalter für die Typüberprüfung ([Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) `Off`ist, ist die `As`-Klausel optional, wenn Sie einen Parameter definieren. Wenn jedoch ein Parameter eine `As`-Klausel verwendet, muss er von allen verwendet werden. Wenn der Schalter für die Typüberprüfung `On`ist, ist die `As`-Klausel für jede Parameterdefinition erforderlich.  
  
     Das Angeben von Datentypen für alle Programmier Elemente wird als *starke Typisierung*bezeichnet. Wenn Sie `Option Strict On`festlegen, erzwingt Visual Basic starke Typisierung. Dies wird aus den folgenden Gründen dringend empfohlen:  
  
    - Sie ermöglicht die IntelliSense-Unterstützung für Ihre Variablen und Parameter. Auf diese Weise können Sie Ihre Eigenschaften und anderen Member anzeigen, wenn Sie Ihren Code eingeben.  
  
    - Der Compiler kann die Typüberprüfung durchführen. Dies hilft bei der Erfassung von Anweisungen, die zur Laufzeit fehlschlagen können, aufgrund von Fehlern wie etwa einem Überlauf. Sie fängt auch Aufrufe von Methoden für Objekte ab, die Sie nicht unterstützen.  
  
    - Dies führt zu einer schnelleren Ausführung des Codes. Ein Grund hierfür ist, dass der Visual Basic Compiler den `Object` Typ zuweist, wenn Sie keinen Datentyp für ein Programmier Element angeben. Der kompilierte Code muss möglicherweise zwischen `Object` und anderen Datentypen hin-und herkonvertiert werden, wodurch die Leistung reduziert wird.  
  
## <a name="see-also"></a>Siehe auch

- [Verfahren](./index.md)
- [Sub-Prozeduren](./sub-procedures.md)
- [Function-Prozeduren](./function-procedures.md)
- [Gewusst wie: Übergeben von Argumenten an eine Prozedur](./how-to-pass-arguments-to-a-procedure.md)
- [Übergeben von Argumenten als Wert und als Verweis](./passing-arguments-by-value-and-by-reference.md)
- [Rekursive Prozeduren](./recursive-procedures.md)
- [Prozedurüberladung](./procedure-overloading.md)
- [Objekte und Klassen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Objektorientierte Programmierung (Visual Basic)](../../concepts/object-oriented-programming.md)
