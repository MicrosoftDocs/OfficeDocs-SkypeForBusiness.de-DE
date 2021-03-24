---
title: Konfigurieren von Skype for Business Server für die Verwendung des einheitlichen Kontaktspeichers
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
ms.openlocfilehash: 9d9601e7a060b6d93a27e872bf05f798d470aa85
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095989"
---
# <a name="configure-skype-for-business-server-to-use-the-unified-contact-store"></a>Konfigurieren von Skype for Business Server für die Verwendung des einheitlichen Kontaktspeichers
 
**Zusammenfassung:** Konfigurieren Sie den einheitlichen Kontaktspeicher für Exchange Server 2016 oder Exchange Server 2013 und Skype for Business Server.
  
Mithilfe des einheitlichen Kontaktspeichers verwalten Benutzer eine einzelne Kontaktliste und verfügen dann über diese Kontakte in mehreren Anwendungen, einschließlich Skype for Business, Microsoft Outlook 2013 und Microsoft Outlook Web App 2013. Wenn Sie den einheitlichen Kontaktspeicher für einen Benutzer aktivieren, werden die Kontakte dieses Benutzers nicht in Skype for Business Server gespeichert und bei Bedarf abgerufen. Stattdessen werden seine Kontakte in Exchange Server 2016 oder Exchange Server 2013 gespeichert und mithilfe von Exchange-Webdiensten abgerufen.
  
> [!NOTE]
> Technisch werden Kontaktinformationen in einem Ordnerpaar gespeichert, das sich im Exchange-Postfach des Benutzers befindet. Die Kontakte selbst werden in einem Ordner namens Skype for Business Contacts gespeichert, der für Endbenutzer sichtbar ist. Metadaten zu den Kontakten werden in einem Unterordner gespeichert, der für Endbenutzer nicht sichtbar ist. 
  
## <a name="enabling-the-unified-contact-store-for-a-user"></a>Aktivieren des einheitlichen Kontaktspeichers für einen Benutzer

Wenn die Server-zu-Server-Authentifizierung zwischen Skype for Business Server und Exchange Server bereits konfiguriert ist, haben Sie auch den einheitlichen Kontaktspeicher aktiviert. es ist keine zusätzliche Serverkonfiguration erforderlich. Beim Benutzerkonto sind jedoch noch Konfigurationsschritte erforderlich, damit die Kontakte des Benutzers in den einheitlichen Kontaktspeicher verschoben werden. Benutzerkontakte werden standardmäßig in Skype for Business Server und nicht im einheitlichen Kontaktspeicher aufbewahrt.
  
Der Zugriff auf den einheitlichen Kontaktspeicher wird mithilfe von Skype for Business Server-Benutzerdienstrichtlinien verwaltet. Benutzerdienste-Richtlinien verfügen nur über eine einzige Eigenschaft (UcsAllowed), die angibt, wo die Kontakte eines Benutzers gespeichert werden. Wenn ein Benutzer von einer Benutzerdienstrichtlinie verwaltet wird, bei der UcsAllowed auf True ($True) festgelegt wurde, werden die Kontakte des Benutzers im einheitlichen Kontaktspeicher gespeichert. Wenn der Benutzer von einer Benutzerdienstrichtlinie verwaltet wird, bei der UcsAllowed auf False ($False) festgelegt wurde, werden seine Kontakte in Skype for Business Server gespeichert.
  
Wenn Sie Skype for Business Server installieren, wird auch eine Richtlinie für einzelne Benutzerdienste (global konfiguriert) installiert. Der Wert UcsAllowed in dieser Richtlinie ist auf True festgelegt, was bedeutet, dass Benutzerkontakte standardmäßig im einheitlichen Kontaktspeicher gespeichert werden (vorausgesetzt, dies wurde bereitgestellt und konfiguriert). Wenn Sie alle Ihre Benutzerkontakte in den einheitlichen Kontaktspeicher migrieren möchten, müssen Sie überhaupt nichts tun. 
  
Wenn Sie nicht alle Kontakte zum einheitlichen Kontaktspeicher migrieren möchten, können Sie den einheitlichen Kontaktspeicher für alle Benutzer deaktivieren, indem Sie die UcsAllowed-Eigenschaft in der globalen Richtlinie auf False festlegen:
  
```powershell
Set-CsUserServicesPolicy -Identity global -UcsAllowed $False
```

Nachdem Sie den einheitlichen Kontaktspeicher in der globalen Richtlinie deaktiviert haben, können Sie eine Benutzerrichtlinie erstellen, die die Verwendung des einheitlichen Kontaktspeichers ermöglicht. Dies ermöglicht es Ihnen, dass einige Benutzer ihre Kontakte im einheitlichen Kontaktspeicher behalten, während andere Benutzer ihre Kontakte weiterhin in Skype for Business Server behalten. Sie können eine Benutzerdienstrichtlinie erstellen, indem Sie einen Befehl wie den folgenden verwenden:
  
```powershell
New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True
```

Nachdem Sie die neue Richtlinie erstellt haben, müssen Sie sie jedem Benutzer zuweisen, der Zugang zum einheitlichen Kontaktspeicher haben soll. Das Zuweisen von benutzerbezogenen Richtlinien zu Benutzern führen Sie mit Befehlen durch, die wie folgt aussehen:
  
```powershell
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"
```

Nachdem die Richtlinie zugewiesen wurde, beginnt Skype for Business Server mit der Migration der Kontakte des Benutzers zum einheitlichen Kontaktspeicher. Nach Abschluss der Migration werden die Kontakte des Benutzers in Exchange und nicht in Skype for Business Server gespeichert. Wenn der Benutzer zum Zeitpunkt des Abschlusses der Migration bei Lync 2013 angemeldet ist, wird ein Meldungsfeld angezeigt, und er wird aufgefordert, sich bei Skype for Business abmelden und sich dann erneut zu melden, um den Prozess zu abschließen. Benutzern, denen diese Benutzerrichtlinie nicht zugewiesen wurde, werden ihre Kontakte nicht zum einheitlichen Kontaktspeicher migriert. Der Grund dafür ist, dass diese Benutzer von der globalen Richtlinie verwaltet werden und die Verwendung des einheitlichen Kontaktspeichers in der globalen Richtlinie deaktiviert wurde.
  
Sie können überprüfen, ob die Kontakte eines Benutzers erfolgreich zum einheitlichen Kontaktspeicher migriert wurden, indem Sie das [Cmdlet Test-CsUnifiedContactStore](/powershell/module/skype/test-csunifiedcontactstore?view=skype-ps) in der Skype for Business Server Management Shell ausführen:
  
```powershell
Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
```

Wenn Test-CsUnifiedContactStore erfolgreich ist, bedeutet dies, dass die Kontakte für den Benutzer sip:kenmyer@ <span></span> litwareinc .com zum einheitlichen Kontaktspeicher <span></span> migriert wurden.
  
## <a name="rolling-back-the-unified-contact-store"></a>Zurückverlegung aus dem einheitlichen Kontaktspeicher

Wenn Sie die Kontakte eines Benutzers aus dem einheitlichen Kontaktspeicher entfernen müssen (z. B. wenn der Benutzer in Microsoft Lync Server 2010 neu vernetzt werden muss und daher den einheitlichen Kontaktspeicher nicht mehr verwenden kann), müssen Sie zwei Dinge tun. Zunächst müssen Sie dem Benutzer eine neue Benutzerdienstrichtlinie zuweisen, die das Speichern von Kontakten im einheitlichen Kontaktspeicher verbietet. (Das heißt, eine Richtlinie, bei der die UcsAllowed-Eigenschaft auf $False.) Wenn Sie nicht über eine solche Richtlinie verfügen, können Sie eine mit einem Befehl wie dem folgenden erstellen:
  
```powershell
New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False
```

Anschließend können Sie diese neue benutzerbezogene Richtlinie (NoUnifiedContactStore) mit dem folgenden Befehl zuweisen:
  
```powershell
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore
```

Dieser Befehl weist die neue Richtlinie dem Benutzer "Ken Myer" zu und verhindert auch, dass dessen Kontakte zum einheitlichen Kontaktspeicher migriert werden.
  
> [!NOTE]
> In einigen Fällen können Sie denselben Nettoeffekt erzielen, indem Sie die Zuweisung der aktuellen Benutzerdienstrichtlinie des Benutzers einfach nicht mehr zuweisen. Das wäre zum Beispiel der Fall, wenn dem Benutzer "Ken Myer" eine benutzerbezogene Benutzerdienste-Richtlinie zugewiesen ist, die den einheitlichen Kontaktspeicher aktiviert, während die globale Richtlinie die Verwendung des einheitlichen Kontaktspeichers verbietet. In diesem Fall können Sie die Zuweisung der Benutzerdienstrichtlinie von Ken nicht mehr zuweisen. Ken würde dann automatisch von der globalen Richtlinie verwaltet werden und somit keinen Zugriff auf den einheitlichen Kontaktspeicher mehr besitzen. Verwenden Sie denselben Befehl wie zuvor gezeigt, um die Zuweisung einer zuvor zugewiesenen Benutzerrichtlinie auf unanfällig zu machen, legen Sie aber dieses Mal den Parameter PolicyName auf einen Nullwert an: Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName $Null 
  
Die Terminologie "verhindert, dass Kens Kontakte zum einheitlichen Kontaktspeicher migriert werden" ist wichtig, wenn Sie mit dem einheitlichen Kontaktspeicher arbeiten. Wenn Sie Ken einfach eine neue Richtlinie für Benutzerdienste zuweisen, werden seine Kontakte nicht aus dem einheitlichen Kontaktspeicher verziehen. Wenn sich ein Benutzer bei Skype for Business Server anmeldet, überprüft das System die Benutzerdienstrichtlinie des Benutzers, um festzustellen, ob seine Kontakte im einheitlichen Kontaktspeicher aufbewahrt werden sollen. Wenn die Antwort ja lautet (d. h. wenn die UcsAllowed-Eigenschaft auf $True festgelegt ist), werden diese Kontakte zum einheitlichen Kontaktspeicher migriert (vorausgesetzt, diese Kontakte befinden sich noch nicht im einheitlichen Kontaktspeicher). Wenn die Antwort nein lautet, ignoriert Skype for Business Server einfach die Kontakte des Benutzers und wechselt zu seiner nächsten Aufgabe. Das bedeutet, dass Skype for Business Server die Kontakte eines Benutzers nicht automatisch aus dem einheitlichen Kontaktspeicher verschiebt, unabhängig vom Wert der UcsAllowed-Eigenschaft.
  
Das bedeutet auch, dass Sie nach dem Zuweisen einer neuen Benutzerdienstrichtlinie das [Cmdlet Invoke-CsUcsRollback](/powershell/module/skype/invoke-csucsrollback?view=skype-ps) ausführen müssen, um die Kontakte des Benutzers aus Exchange Server und zurück zu Skype for Business Server zu verschieben. Beispiel: Nachdem Sie dem Benutzer "Ken Myer" eine neue Benutzerdienste-Richtlinie zugewiesen haben, können Sie seine Kontakte mit dem folgenden Befehl aus dem einheitlichen Kontaktspeicher verlegen:
  
```powershell
Invoke-CsUcsRollback -Identity "Ken Myer"
```

Wenn Sie die Benutzerdienste-Richtlinie ändern, ohne anschließend das Invoke-CsUcsRollback-Cmdlet auszuführen, bleiben die Kontakte von Ken im einheitlichen Kontaktspeicher. Und was wäre, wenn Sie das Invoke-CsUcsRollback-Cmdlet ausführen, ohne die Benutzerdienste-Richtlinie von Ken Myer zu ändern? In diesem Fall werden die Kontakte von Ken nur vorübergehend aus dem einheitlichen Kontaktspeicher entfernt. Achten Sie hierbei bitte auf das Wort "vorübergehend"! Nachdem Kens Kontakte aus dem einheitlichen Kontaktspeicher entfernt wurden, wartet Skype for Business Server 7 Tage und überprüft dann, welche Benutzerdienstrichtlinie Ken zugewiesen wurde. Wenn Ken weiterhin eine Richtlinie zugewiesen ist, die ihn für den einheitlichen Kontaktspeicher aktiviert, werden seine Kontakte automatisch wieder zurück in den Kontaktspeicher verschoben. Um die Kontakte dauerhaft aus dem einheitlichen Kontaktspeicher zu entfernen, müssen Sie nicht nur das Invoke-CsUcsRollback-Cmdlet ausführen, sondern zusätzlich auch seine Benutzerdienste-Richtlinie ändern.
  
Aufgrund der großen Anzahl von Variablen, die sich auf die Migration auswirken können, ist es schwierig zu schätzen, wie lange es dauert, bis Konten vollständig zum einheitlichen Kontaktspeicher migriert werden. In der Regel wird die Migration jedoch nicht sofort wirksam: Selbst bei der Migration einer kleinen Anzahl von Kontakten kann es 10 Minuten oder mehr dauern, bis die Migration abgeschlossen ist.
