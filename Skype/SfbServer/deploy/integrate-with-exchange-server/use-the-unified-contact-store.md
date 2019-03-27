---
title: Konfigurieren von Skype for Business Server für die Verwendung des einheitlichen Kontaktspeichers
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6aa17ae3-764e-4986-a900-85a3cdb8c1fc
description: 'Zusammenfassung: Konfigurieren des vereinheitlichte kontaktspeichers für Exchange Server und Skype für Business Server.'
ms.openlocfilehash: fd58c0cfd86092bb1a6004ac4d70c98c51062ea1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30888682"
---
# <a name="configure-skype-for-business-server-to-use-the-unified-contact-store"></a>Konfigurieren von Skype for Business Server für die Verwendung des einheitlichen Kontaktspeichers
 
**Zusammenfassung:** Konfigurieren Sie den vereinheitlichte Kontakte Speicher für Exchange Server 2016 oder Exchange Server 2013 und Skype für Business Server.
  
Mit dem einheitlichen Kontaktspeicher, Benutzer verwalten eine einzigen Kontaktliste und dann die Kontakte in mehreren Anwendungen, einschließlich Skype für Unternehmen, Microsoft Outlook 2013 und Microsoft Outlook Web App 2013 verfügbar. Wenn Sie den einheitlichen Kontaktspeicher für einen Benutzer aktivieren, dass Kontakte des Benutzers werden nicht in Skype für Business Server gespeichert und bei Bedarf abgerufen. Stattdessen auch seiner Kontakte werden in Exchange Server 2016 oder Exchange Server 2013 gespeichert und abgerufen werden, mithilfe der Exchange-Webdienste.
  
> [!NOTE]
> Kontaktinformationen ist technisch gesehen, in einem Paar von Ordner in Exchange-Postfach des Benutzers gespeichert. Die Kontakte selbst werden gespeichert, in einen Ordner namens Skype für Geschäftskontakte das für Endbenutzer angezeigt wird. Metadaten für die Kontakte befinden sich in einem Unterordner, der für Endbenutzer nicht sichtbar ist. 
  
## <a name="enabling-the-unified-contact-store-for-a-user"></a>Aktivieren des einheitlichen Kontaktspeichers für einen Benutzer

Wenn der Server-zu-Server-Authentifizierung zwischen Skype für Business Server und Exchange Server bereits konfiguriert ist, haben Sie auch den einheitlichen Kontaktspeicher aktiviert; Es ist keine zusätzliche Konfiguration erforderlich. Beim Benutzerkonto sind jedoch noch Konfigurationsschritte erforderlich, damit die Kontakte des Benutzers in den einheitlichen Kontaktspeicher verschoben werden. Standardmäßig werden Benutzerkontakte in Skype für Business Server und nicht in den einheitlichen Kontaktspeicher gespeichert.
  
Zugriff auf den einheitlichen Kontaktspeicher wird mithilfe von Skype für Business Server Services Benutzerrichtlinien verwaltet. Benutzerdienst-Richtlinien verfügen nur über eine einzige Eigenschaft (UcsAllowed), die angibt, wo die Kontakte eines Benutzers gespeichert werden. Wenn ein Benutzer durch eine benutzerdiensterichtlinie verwaltet wird, in dem UcsAllowed auf "true" ($True) festgelegt wurde, werden Kontakte des Benutzers in dem einheitlichen Kontaktspeicher gespeichert. Wenn der Benutzer von verwaltet wird benutzerdiensterichtlinie ein Benutzers, in dem UcsAllowed auf "false" ($False) festgelegt wurde, dann werden auch seiner Kontakte in Skype für Business Server gespeichert.
  
Wenn Sie Skype für Business Server installieren, wird eine einzelne benutzerdiensterichtlinie (auf globaler Ebene konfiguriert) ebenfalls installiert. Der Wert „UcsAllowed“ in dieser Richtlinie ist auf „True“ festgelegt, was bedeutet, dass Benutzerkontakte standardmäßig im einheitlichen Kontaktspeicher gespeichert werden (vorausgesetzt, dass dieser bereitgestellt und konfiguriert wurde). Wenn Sie alle Benutzerkontakte zum einheitlichen Kontaktspeicher migrieren möchten, müssen Sie nichts weiter tun. 
  
Wenn Sie lieber nicht alle Kontakte zum einheitlichen Kontaktspeicher migrieren möchten, können Sie den einheitlichen Kontaktspeicher für alle Benutzer deaktivieren, indem Sie die Eigenschaft „UcsAllowed“ in der globalen Richtlinie auf „False“ setzen:
  
```
Set-CsUserServicesPolicy -Identity global -UcsAllowed $False
```

Nachdem Sie den einheitlichen Kontaktspeicher in der globalen Richtlinie deaktiviert haben können Sie eine benutzerbasierte Richtlinie erstellen, die die Verwendung des einheitlichen Kontaktspeicher ermöglicht. Dadurch können Sie einige Benutzer ihre Kontakte in den einheitlichen Kontaktspeicher behalten, während andere Benutzer weiterhin behalten ihre Kontakte in Skype für Business Server verfügen. Sie können eine benutzerspezifische benutzerdiensterichtlinie erstellen, mit einem Befehl wie den folgenden:
  
```
New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True
```

Nachdem Sie die neue Richtlinie erstellt haben, müssen Sie sie jedem Benutzer zuweisen, der Zugang zum einheitlichen Kontaktspeicher haben soll. Das Zuweisen von benutzerbezogenen Richtlinien zu Benutzern führen Sie mit Befehlen wie dem folgenden durch:
  
```
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"
```

Wenn die Richtlinie zugewiesen wurde, beginnt Skype für Business Server die Kontakte des Benutzers zum einheitlichen Kontaktspeicher migriert. Nach Abschluss der Migration müssen der Benutzer auch seiner Kontakte in Exchange statt Skype für Business Server gespeichert. Falls der Benutzer angemeldet sein, um Lync 2013 an die Zeit Migration abgeschlossen ist, wird ein Meldungsfeld angezeigt, und er aufgefordert werden, melden Sie sich für Unternehmen Skype und dann erneut anmelden, um den Vorgang abzuschließen. Die Kontakte von Benutzern, denen diese benutzerbezogene Richtlinie zugewiesen wurde, werden nicht zum einheitlichen Kontaktspeicher migriert. Dies liegt daran diese Benutzer werden durch die globale Richtlinie verwaltet wird und Verwendung des einheitlichen Kontaktspeicher in der globalen Richtlinie deaktiviert wurde.
  
Sie können überprüfen, ob die Kontakte eines Benutzers durch Ausführen des [Test-CsUnifiedContactStore](https://docs.microsoft.com/powershell/module/skype/test-csunifiedcontactstore?view=skype-ps) -Cmdlets in der Skype für Business Server-Verwaltungsshell erfolgreich zum einheitlichen Kontaktspeicher migriert wurden:
  
```
Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
```

Wenn der Test-CsUnifiedContactStore erfolgreich, die bedeutet, dass die Kontakte für den Benutzer Sip: Kenmyer @<span></span>Litwareinc<span></span>.com zum einheitlichen Kontaktspeicher migriert wurden.
  
## <a name="rolling-back-the-unified-contact-store"></a>Zurückverlegung aus dem einheitlichen Kontaktspeicher

Wenn Sie Kontakte eines Benutzers aus dem einheitlichen Kontaktspeicher entfernen (z. B., wenn der Benutzer muss auf Microsoft Lync Server 2010 verlagert werden und kann nicht mehr dem einheitlichen Kontaktspeicher verwenden) müssen, müssen Sie zwei Dinge tun. Erstens müssen Sie dem Benutzer eine neue benutzerdiensterichtlinie, eine zuweisen, die verhindert, dass das Speichern von Kontakten in der einheitliche Kontaktspeicher. (D. h., eine Richtlinie, in dem die UcsAllowed-Eigenschaft wurde auf $False festgelegt.) Wenn Sie nicht über eine solche Richtlinie verfügen, können Sie eine mit einem Befehl wie den folgenden erstellen:
  
```
New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False
```

Anschließend können Sie diese neue benutzerbezogene Richtlinie (NoUnifiedContactStore) mit dem folgenden Befehl zuweisen:
  
```
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore
```

Dieser Befehl weist die neue Richtlinie dem Benutzer „Ken Myer“ zu und verhindert, dass dessen Kontakte zum einheitlichen Kontaktspeicher migriert werden.
  
> [!NOTE]
> In manchen Fällen können Sie den gleichen Effekt erzielen, indem Sie einfach die Zuweisung der aktuellen Benutzerdienst-Richtlinie für den Benutzer aufheben. Das wäre z. B. der Fall, wenn dem Benutzer „Ken Myer“ eine benutzerbezogene Benutzerdienst-Richtlinie zugewiesen ist, die den einheitlichen Kontaktspeicher aktiviert, während die globale Richtlinie die Verwendung des einheitlichen Kontaktspeichers verbietet. In einem solchen Fall können Sie die Zuweisung der benutzerbezogenen Benutzerdienste-Richtlinie für Ken aufheben. Ken würde dann automatisch von der globalen Richtlinie verwaltet werden und somit keinen Zugriff auf den einheitlichen Kontaktspeicher mehr besitzen. Verwenden Sie zur Zuweisung einer zuvor zugewiesenen benutzerspezifischen Richtlinie im gleichen Befehl Siehe vor, aber diesmal den Parameter "PolicyName" auf einen null-Wert festgelegt: "Grant-csuserservicespolicy"-Identity "Ken Myer" - PolicyName $Null 
  
Die Begriffe "dessen Kontakte verhindert, dass zum einheitlichen Kontaktspeicher migriert" ist wichtig, im Hinterkopf behalten beim Arbeiten mit dem einheitlichen Kontaktspeicher. Einfach zuweisen Ken wird eine neue benutzerdiensterichtlinie nicht seine Kontakte aus dem einheitlichen Kontaktspeicher verschoben. Wenn ein Benutzer bei Skype für Business Server anmeldet, überprüft das System des Benutzers benutzerdiensterichtlinie, um festzustellen, ob auch seiner Kontakte in den einheitlichen Kontaktspeicher abgelegt werden soll. Wenn die Antwort "Ja" ist (d. h., wenn die UcsAllowed-Eigenschaft auf $True festgelegt ist) werden die Kontakte migriert werden, zum einheitlichen Kontaktspeicher (vorausgesetzt, dass die Kontakte nicht bereits in dem einheitlichen Kontaktspeicher sind). Ist die Antwort Nein, klicken Sie dann Skype für Business Server einfach die Kontakte des Benutzers ignoriert und fährt mit der nächsten Aufgabe. Dies bedeutet, dass Skype für Business Server nicht automatisch Kontakte eines Benutzers aus dem einheitlichen Kontaktspeicher, unabhängig vom Wert der Eigenschaft UcsAllowed verschoben wird.
  
Das bedeutet auch, dass nach dem Zuweisen des Benutzers einer neue benutzerdiensterichtlinie, Sie das Cmdlet " [Invoke-CsUcsRollback](https://docs.microsoft.com/powershell/module/skype/invoke-csucsrollback?view=skype-ps) " ausführen müssen, um die Kontakte des Benutzers Exchange Server und wieder in Skype für Business Server zu verschieben. Beispiel: Nachdem Sie dem Benutzer „Ken Myer“ eine neue Benutzerdienst-Richtlinie zugewiesen haben, können Sie seine Kontakte mit dem folgenden Befehl aus dem einheitlichen Kontaktspeicher verlegen:
  
```
Invoke-CsUcsRollback -Identity "Ken Myer"
```

Wenn Sie die Benutzerdienst-Richtlinie ändern, ohne anschließend das Cmdlet Invoke-CsUcsRollback auszuführen, bleiben die Kontakte von Ken im einheitlichen Kontaktspeicher. Und was wäre, wenn Sie das Invoke-CsUcsRollback-Cmdlet ausführen, ohne die Benutzerdienste-Richtlinie von Ken Myer zu ändern? In diesem Fall werden die Kontakte von Ken nur vorübergehend aus dem einheitlichen Kontaktspeicher entfernt. Achten Sie hierbei bitte auf das Wort „vorübergehend“! Nach dessen Kontakte aus dem einheitlichen Kontaktspeicher entfernt wurden, werden Skype für Business Server warten Sie 7 Tage und überprüfen Sie dann, um herauszufinden, welche Dienste Benutzerrichtlinie Ken zugewiesen wurde. Wenn Ken weiterhin eine Richtlinie zugewiesen ist, die ihn für den einheitlichen Kontaktspeicher aktiviert, werden seine Kontakte automatisch wieder zurück in den Kontaktspeicher verschoben. Um die Kontakte dauerhaft aus dem einheitlichen Kontaktspeicher zu entfernen, müssen Sie nicht nur das Invoke-CsUcsRollback-Cmdlet ausführen, sondern zusätzlich auch seine Benutzerdienste-Richtlinie ändern.
  
Aufgrund der zahlreichen Variablen, die sich auf die Migration auswirken können, kann schwer geschätzt werden, wie viel Zeit erforderlich ist, bis Konten vollständig zum einheitlichen Kontaktspeicher migriert sind. Als allgemeine Regel lässt sich jedoch sagen, dass die Migration nicht unmittelbar in Kraft tritt: Auch wenn Sie nur sehr wenige Kontakte migrieren, kann es zehn Minuten oder länger dauern, bis die Verschiebung abgeschlossen ist.
  

