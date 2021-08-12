---
title: Konfigurieren Skype for Business Server für die Verwendung des einheitlichen Kontaktspeichers
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6aa17ae3-764e-4986-a900-85a3cdb8c1fc
description: 'Zusammenfassung: Konfigurieren des einheitlichen Kontaktspeichers für Exchange Server und Skype for Business Server.'
ms.openlocfilehash: 78953049394391517d229205e711e670701d9f857458673646e4022a178d3843
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54295712"
---
# <a name="configure-skype-for-business-server-to-use-the-unified-contact-store"></a>Konfigurieren Skype for Business Server für die Verwendung des einheitlichen Kontaktspeichers
 
**Zusammenfassung:** Konfigurieren Sie den einheitlichen Kontaktspeicher für Exchange Server 2016 oder Exchange Server 2013 und Skype for Business Server.
  
Mithilfe des einheitlichen Kontaktspeichers verwalten Benutzer eine einzelne Kontaktliste und haben diese Kontakte dann in mehreren Anwendungen verfügbar, einschließlich Skype for Business, Microsoft Outlook 2013 und Microsoft Outlook Web App 2013. Wenn Sie den einheitlichen Kontaktspeicher für einen Benutzer aktivieren, werden die Kontakte dieses Benutzers nicht in Skype for Business Server gespeichert und bei Bedarf abgerufen. Stattdessen werden seine Kontakte in Exchange Server 2016 oder Exchange Server 2013 gespeichert und mithilfe Exchange Webdienste abgerufen.
  
> [!NOTE]
> Technisch gesehen werden Kontaktinformationen in einem Ordnerpaar gespeichert, das sich im postfach Exchange des Benutzers befindet. Die Kontakte selbst werden in einem Ordner mit dem Namen Skype for Business Kontakte gespeichert, der für Endbenutzer sichtbar ist. Metadaten zu den Kontakten werden in einem Unterordner gespeichert, der für Endbenutzer nicht sichtbar ist. 
  
## <a name="enabling-the-unified-contact-store-for-a-user"></a>Aktivieren des einheitlichen Kontaktspeichers für einen Benutzer

Wenn die Server-zu-Server-Authentifizierung zwischen Skype for Business Server und Exchange Server bereits konfiguriert ist, haben Sie auch den einheitlichen Kontaktspeicher aktiviert. Es ist keine zusätzliche Serverkonfiguration erforderlich. Beim Benutzerkonto sind jedoch noch Konfigurationsschritte erforderlich, damit die Kontakte des Benutzers in den einheitlichen Kontaktspeicher verschoben werden. Standardmäßig werden Benutzerkontakte in Skype for Business Server und nicht im einheitlichen Kontaktspeicher gespeichert.
  
Der Zugriff auf den einheitlichen Kontaktspeicher wird mithilfe Skype for Business Server Benutzerdienstrichtlinien verwaltet. Benutzerdienste-Richtlinien verfügen nur über eine einzige Eigenschaft (UcsAllowed), die angibt, wo die Kontakte eines Benutzers gespeichert werden. Wenn ein Benutzer von einer Benutzerdienstrichtlinie verwaltet wird, bei der UcsAllowed auf "True" ($True) festgelegt wurde, werden die Kontakte des Benutzers im einheitlichen Kontaktspeicher gespeichert. Wenn der Benutzer von einer Benutzerdienstrichtlinie verwaltet wird, bei der UcsAllowed auf "False" ($False) festgelegt wurde, werden seine Kontakte in Skype for Business Server gespeichert.
  
Wenn Sie Skype for Business Server installieren, wird auch eine einzelne Benutzerdienstrichtlinie (auf globaler Ebene konfiguriert) installiert. Der UcsAllowed-Wert in dieser Richtlinie ist auf "True" festgelegt, was bedeutet, dass Benutzerkontakte standardmäßig im einheitlichen Kontaktspeicher gespeichert werden (vorausgesetzt, dass dies bereitgestellt und konfiguriert wurde). Wenn Sie alle Ihre Benutzerkontakte zum einheitlichen Kontaktspeicher migrieren möchten, müssen Sie überhaupt nichts tun. 
  
Wenn Sie nicht alle Kontakte zum einheitlichen Kontaktspeicher migrieren möchten, können Sie den einheitlichen Kontaktspeicher für alle Benutzer deaktivieren, indem Sie die UcsAllowed-Eigenschaft in der globalen Richtlinie auf "False" festlegen:
  
```powershell
Set-CsUserServicesPolicy -Identity global -UcsAllowed $False
```

Nachdem Sie den einheitlichen Kontaktspeicher in der globalen Richtlinie deaktiviert haben, können Sie eine Benutzerrichtlinie erstellen, die die Verwendung des einheitlichen Kontaktspeichers ermöglicht. Auf diese Weise können Sie festlegen, dass einige Benutzer ihre Kontakte im einheitlichen Kontaktspeicher aufbewahren, während andere Benutzer ihre Kontakte weiterhin in Skype for Business Server. Sie können eine benutzerspezifische Benutzerdienstrichtlinie mithilfe eines Befehls wie dem folgenden erstellen:
  
```powershell
New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True
```

Nachdem Sie die neue Richtlinie erstellt haben, müssen Sie sie jedem Benutzer zuweisen, der Zugang zum einheitlichen Kontaktspeicher haben soll. Das Zuweisen von benutzerbezogenen Richtlinien zu Benutzern führen Sie mit Befehlen durch, die wie folgt aussehen:
  
```powershell
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"
```

Nachdem die Richtlinie zugewiesen wurde, beginnen Skype for Business Server mit der Migration der Kontakte des Benutzers zum einheitlichen Kontaktspeicher. Nach Abschluss der Migration werden die Kontakte des Benutzers in Exchange statt in Skype for Business Server gespeichert. Wenn der Benutzer zum Zeitpunkt der Migration bei Lync 2013 angemeldet ist, wird ein Meldungsfeld angezeigt, und er wird aufgefordert, sich von Skype for Business abzumelden und sich dann wieder anzumelden, um den Prozess abzuschließen. Benutzern, denen diese Benutzerrichtlinie nicht zugewiesen wurde, werden ihre Kontakte nicht zum einheitlichen Kontaktspeicher migriert. Der Grund dafür ist, dass diese Benutzer von der globalen Richtlinie verwaltet werden und die Verwendung des einheitlichen Kontaktspeichers in der globalen Richtlinie deaktiviert wurde.
  
Sie können überprüfen, ob die Kontakte eines Benutzers erfolgreich in den einheitlichen Kontaktspeicher migriert wurden, indem Sie das Cmdlet ["Test-CsUnifiedContactStore"](/powershell/module/skype/test-csunifiedcontactstore?view=skype-ps) in der Skype for Business Server-Verwaltungsshell ausführen:
  
```powershell
Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
```

Wenn Test-CsUnifiedContactStore erfolgreich ist, bedeutet dies, dass die Kontakte für den Benutzer "sip:kenmyer@ <span></span> litwareinc <span></span> .com" zum einheitlichen Kontaktspeicher migriert wurden.
  
## <a name="rolling-back-the-unified-contact-store"></a>Zurückverlegung aus dem einheitlichen Kontaktspeicher

Wenn Sie die Kontakte eines Benutzers aus dem einheitlichen Kontaktspeicher entfernen müssen (z. B. wenn der Benutzer in Microsoft Lync Server 2010 neu hinzugefügt werden muss und daher den einheitlichen Kontaktspeicher nicht mehr verwenden kann), müssen Sie zwei Dinge tun. Zunächst müssen Sie dem Benutzer eine neue Benutzerdienstrichtlinie zuweisen, die das Speichern von Kontakten im einheitlichen Kontaktspeicher verbietet. (Das heißt, eine Richtlinie, bei der die UcsAllowed-Eigenschaft auf $False festgelegt wurde.) Wenn Sie nicht über eine solche Richtlinie verfügen, können Sie eine mit einem Befehl wie dem folgenden erstellen:
  
```powershell
New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False
```

Anschließend können Sie diese neue benutzerbezogene Richtlinie (NoUnifiedContactStore) mit dem folgenden Befehl zuweisen:
  
```powershell
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore
```

Dieser Befehl weist die neue Richtlinie dem Benutzer "Ken Myer" zu und verhindert auch, dass dessen Kontakte zum einheitlichen Kontaktspeicher migriert werden.
  
> [!NOTE]
> In einigen Fällen können Sie denselben Nettoeffekt erzielen, indem Sie einfach die Zuweisung der aktuellen Benutzerdienstrichtlinie des Benutzers aufheben. Das wäre zum Beispiel der Fall, wenn dem Benutzer "Ken Myer" eine benutzerbezogene Benutzerdienste-Richtlinie zugewiesen ist, die den einheitlichen Kontaktspeicher aktiviert, während die globale Richtlinie die Verwendung des einheitlichen Kontaktspeichers verbietet. In diesem Fall können Sie die Benutzerdienstrichtlinie von Ken aufheben. Ken würde dann automatisch von der globalen Richtlinie verwaltet werden und somit keinen Zugriff auf den einheitlichen Kontaktspeicher mehr besitzen. Um die Zuweisung einer zuvor zugewiesenen benutzerbasierten Richtlinie aufzuheben, verwenden Sie denselben Befehl wie zuvor gezeigt. Legen Sie diesmal jedoch den Parameter "PolicyName" auf einen Nullwert fest: Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName $Null 
  
Die Terminologie "verhindert, dass Kens Kontakte in den einheitlichen Kontaktspeicher migriert werden" ist wichtig, wenn Sie mit dem einheitlichen Kontaktspeicher arbeiten. Wenn Sie Ken einfach eine neue Benutzerdienstrichtlinie zuweisen, werden seine Kontakte nicht aus dem einheitlichen Kontaktspeicher verschoben. Wenn sich ein Benutzer bei Skype for Business Server anmeldet, überprüft das System die Benutzerdienstrichtlinie des Benutzers, um festzustellen, ob seine Kontakte im einheitlichen Kontaktspeicher aufbewahrt werden sollen. Wenn die Antwort "Ja" lautet (das heißt, wenn die UcsAllowed-Eigenschaft auf $True festgelegt ist), werden diese Kontakte in den einheitlichen Kontaktspeicher migriert (vorausgesetzt, dass sich diese Kontakte nicht bereits im einheitlichen Kontaktspeicher befinden). Wenn die Antwort "Nein" lautet, ignoriert Skype for Business Server einfach die Kontakte des Benutzers und geht zur nächsten Aufgabe über. Das bedeutet, dass Skype for Business Server die Kontakte eines Benutzers nicht automatisch aus dem einheitlichen Kontaktspeicher verschieben, unabhängig vom Wert der UcsAllowed-Eigenschaft.
  
Das bedeutet auch, dass Sie nach dem Zuweisen einer neuen Benutzerdienstrichtlinie für den Benutzer das Cmdlet [Invoke-CsUcsRollback](/powershell/module/skype/invoke-csucsrollback?view=skype-ps) ausführen müssen, um die Kontakte des Benutzers aus Exchange Server und zurück zu Skype for Business Server zu verschieben. Beispiel: Nachdem Sie dem Benutzer "Ken Myer" eine neue Benutzerdienste-Richtlinie zugewiesen haben, können Sie seine Kontakte mit dem folgenden Befehl aus dem einheitlichen Kontaktspeicher verlegen:
  
```powershell
Invoke-CsUcsRollback -Identity "Ken Myer"
```

Wenn Sie die Benutzerdienste-Richtlinie ändern, ohne anschließend das Invoke-CsUcsRollback-Cmdlet auszuführen, bleiben die Kontakte von Ken im einheitlichen Kontaktspeicher. Und was wäre, wenn Sie das Invoke-CsUcsRollback-Cmdlet ausführen, ohne die Benutzerdienste-Richtlinie von Ken Myer zu ändern? In diesem Fall werden die Kontakte von Ken nur vorübergehend aus dem einheitlichen Kontaktspeicher entfernt. Achten Sie hierbei bitte auf das Wort "vorübergehend"! Nachdem Kens Kontakte aus dem einheitlichen Kontaktspeicher entfernt wurden, wartet Skype for Business Server 7 Tage und überprüft dann, welche Benutzerdienstrichtlinie Ken zugewiesen wurde. Wenn Ken weiterhin eine Richtlinie zugewiesen ist, die ihn für den einheitlichen Kontaktspeicher aktiviert, werden seine Kontakte automatisch wieder zurück in den Kontaktspeicher verschoben. Um die Kontakte dauerhaft aus dem einheitlichen Kontaktspeicher zu entfernen, müssen Sie nicht nur das Invoke-CsUcsRollback-Cmdlet ausführen, sondern zusätzlich auch seine Benutzerdienste-Richtlinie ändern.
  
Aufgrund der großen Anzahl von Variablen, die sich auf die Migration auswirken können, ist es schwierig zu schätzen, wie lange es dauert, bis Konten vollständig in den einheitlichen Kontaktspeicher migriert werden. In der Regel wird die Migration jedoch nicht sofort wirksam: Selbst bei der Migration einer kleinen Anzahl von Kontakten kann es 10 Minuten oder mehr dauern, bis die Verschiebung abgeschlossen ist.
