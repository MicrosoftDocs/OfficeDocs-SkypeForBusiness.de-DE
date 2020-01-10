---
title: Konfigurieren von Skype for Business Server für die Verwendung des einheitlichen Kontaktspeichers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6aa17ae3-764e-4986-a900-85a3cdb8c1fc
description: 'Zusammenfassung: Konfigurieren des Unified Contacts Store für Exchange Server und Skype for Business Server.'
ms.openlocfilehash: 7a52a6bf648632daac416dcf6ffd4fd4149804c0
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003555"
---
# <a name="configure-skype-for-business-server-to-use-the-unified-contact-store"></a>Konfigurieren von Skype for Business Server für die Verwendung des einheitlichen Kontaktspeichers
 
**Zusammenfassung:** Konfigurieren Sie den Unified Contacts Store für Exchange Server 2016 oder Exchange Server 2013 und Skype for Business Server.
  
Mithilfe des einheitlichen Kontaktspeichers pflegen Benutzer eine einzelne Kontaktliste und können diese Kontakte dann in mehreren Anwendungen wie Skype for Business, Microsoft Outlook 2013 und Microsoft Outlook Web App 2013 zur Verfügung stellen. Wenn Sie den Unified Contact Store für einen Benutzer aktivieren, werden die Kontakte dieses Benutzers nicht in Skype for Business Server gespeichert und nach Bedarf abgerufen. Stattdessen werden seine Kontakte in Exchange Server 2016 oder Exchange Server 2013 gespeichert und mithilfe von Exchange-Webdiensten abgerufen.
  
> [!NOTE]
> Technisch gesehen werden Kontaktinformationen in einem Paar von Ordnern gespeichert, die im Exchange-Postfach des Benutzers gefunden werden. Die Kontakte werden in einem Ordner namens "Skype for Business-Kontakte" gespeichert, der für die Endbenutzer sichtbar ist. Metadaten zu den Kontakten werden in einem Unterordner gespeichert, der für Endbenutzer nicht sichtbar ist. 
  
## <a name="enabling-the-unified-contact-store-for-a-user"></a>Aktivieren des einheitlichen Kontaktspeichers für einen Benutzer

Wenn die Server-zu-Server-Authentifizierung zwischen Skype for Business Server und Exchange Server bereits konfiguriert ist, haben Sie den Unified Contact Store ebenfalls aktiviert. Es ist keine zusätzliche Serverkonfiguration erforderlich. Beim Benutzerkonto sind jedoch noch Konfigurationsschritte erforderlich, damit die Kontakte des Benutzers in den einheitlichen Kontaktspeicher verschoben werden. Standardmäßig werden Benutzer Kontakte in Skype for Business Server und nicht im Unified Contact Store aufbewahrt.
  
Der Zugriff auf den einheitlichen Kontaktspeicher wird mithilfe von Skype for Business Server-Benutzer Dienst Richtlinien verwaltet. Benutzerdienst-Richtlinien verfügen nur über eine einzige Eigenschaft (UcsAllowed), die angibt, wo die Kontakte eines Benutzers gespeichert werden. Wenn ein Benutzer von einer Richtlinie für Benutzer Dienste verwaltet wird, in der UcsAllowed auf "true" ($true) festgelegt wurde, werden die Kontakte des Benutzers im Unified Contact Store gespeichert. Wenn der Benutzer von einer Richtlinie für Benutzer Dienste verwaltet wird, in der UcsAllowed auf "false" ($false) festgelegt wurde, werden seine Kontakte in Skype for Business Server gespeichert.
  
Wenn Sie Skype for Business Server installieren, wird auch eine Richtlinie für einzelne Benutzer Dienste installiert, die auf dem globalen Bereich konfiguriert ist. Der Wert „UcsAllowed“ in dieser Richtlinie ist auf „True“ festgelegt, was bedeutet, dass Benutzerkontakte standardmäßig im einheitlichen Kontaktspeicher gespeichert werden (vorausgesetzt, dass dieser bereitgestellt und konfiguriert wurde). Wenn Sie alle Benutzerkontakte zum einheitlichen Kontaktspeicher migrieren möchten, müssen Sie nichts weiter tun. 
  
Wenn Sie lieber nicht alle Kontakte zum einheitlichen Kontaktspeicher migrieren möchten, können Sie den einheitlichen Kontaktspeicher für alle Benutzer deaktivieren, indem Sie die Eigenschaft „UcsAllowed“ in der globalen Richtlinie auf „False“ setzen:
  
```powershell
Set-CsUserServicesPolicy -Identity global -UcsAllowed $False
```

Nachdem Sie den Unified Contact Store in der globalen Richtlinie deaktiviert haben, können Sie eine benutzerspezifische Richtlinie erstellen, die die Verwendung des einheitlichen Kontaktspeichers ermöglicht. auf diese Weise können einige Benutzer Ihre Kontakte im Unified Contact Store behalten, während andere Benutzer weiterhin Ihre Kontakte in Skype for Business Server behalten. Sie können eine Benutzer dienstrichtlinie pro Benutzer erstellen, indem Sie einen Befehl wie den folgenden verwenden:
  
```powershell
New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True
```

Nachdem Sie die neue Richtlinie erstellt haben, müssen Sie sie jedem Benutzer zuweisen, der Zugang zum einheitlichen Kontaktspeicher haben soll. Das Zuweisen von benutzerbezogenen Richtlinien zu Benutzern führen Sie mit Befehlen wie dem folgenden durch:
  
```powershell
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"
```

Nachdem die Richtlinie zugewiesen wurde, wird Skype for Business Server beginnen, die Kontakte des Benutzers in den Unified Contact Store zu migrieren. Nach Abschluss der Migration werden die Kontakte in Exchange anstatt in Skype for Business Server gespeichert. Wenn der Benutzer zu dem Zeitpunkt, zu dem die Migration abgeschlossen ist, bei lync 2013 angemeldet ist, wird ein Meldungsfeld angezeigt, in dem er oder Sie aufgefordert wird, sich von Skype for Business abzumelden und dann erneut anzumelden, um den Vorgang abzuschließen. Die Kontakte von Benutzern, denen diese benutzerbezogene Richtlinie zugewiesen wurde, werden nicht zum einheitlichen Kontaktspeicher migriert. Dies liegt daran, dass diese Benutzer von der globalen Richtlinie verwaltet werden und die Verwendung des Unified Contact Store in der globalen Richtlinie deaktiviert wurde.
  
Sie können überprüfen, ob die Kontakte eines Benutzers erfolgreich in den Unified Contact Store migriert wurden, indem Sie das Cmdlet [Test-CsUnifiedContactStore](https://docs.microsoft.com/powershell/module/skype/test-csunifiedcontactstore?view=skype-ps) in der Skype for Business Server-Verwaltungsshell ausführen:
  
```powershell
Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
```

Wenn Test-CsUnifiedContactStore erfolgreich ist, bedeutet dies, dass die Kontakte für den Benutzer SIP<span></span>:<span></span>kenmyer@ "litwareinc. com in den einheitlichen Kontaktspeicher migriert wurden.
  
## <a name="rolling-back-the-unified-contact-store"></a>Zurückverlegung aus dem einheitlichen Kontaktspeicher

Wenn Sie die Kontakte eines Benutzers aus dem Unified Contact Store entfernen müssen (wenn der Benutzer beispielsweise auf Microsoft lync Server 2010 verlagert werden muss und daher den einheitlichen Kontaktspeicher nicht mehr verwenden kann), müssen Sie zwei Schritte ausführen. Zunächst müssen Sie dem Benutzer eine neue Richtlinie für Benutzer Dienste zuweisen, die verhindert, dass Kontakte im Unified Contact Store gespeichert werden. (Dies ist eine Richtlinie, bei der die UcsAllowed-Eigenschaft auf $false festgesetzt wurde.) Wenn Sie nicht über eine solche Richtlinie verfügen, können Sie Sie mithilfe eines Befehls wie den folgenden erstellen:
  
```powershell
New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False
```

Anschließend können Sie diese neue benutzerbezogene Richtlinie (NoUnifiedContactStore) mit dem folgenden Befehl zuweisen:
  
```powershell
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore
```

Dieser Befehl weist die neue Richtlinie dem Benutzer „Ken Myer“ zu und verhindert, dass dessen Kontakte zum einheitlichen Kontaktspeicher migriert werden.
  
> [!NOTE]
> In manchen Fällen können Sie den gleichen Effekt erzielen, indem Sie einfach die Zuweisung der aktuellen Benutzerdienst-Richtlinie für den Benutzer aufheben. Das wäre z. B. der Fall, wenn dem Benutzer „Ken Myer“ eine benutzerbezogene Benutzerdienst-Richtlinie zugewiesen ist, die den einheitlichen Kontaktspeicher aktiviert, während die globale Richtlinie die Verwendung des einheitlichen Kontaktspeichers verbietet. In einem solchen Fall können Sie die Zuweisung der benutzerbezogenen Benutzerdienste-Richtlinie für Ken aufheben. Ken würde dann automatisch von der globalen Richtlinie verwaltet werden und somit keinen Zugriff auf den einheitlichen Kontaktspeicher mehr besitzen. Wenn Sie eine zuvor zugewiesene pro-Benutzer-Richtlinie nicht zuweisen möchten, verwenden Sie den gleichen Befehl wie zuvor, aber dieses Mal legen Sie den Parameter "PolicyName" auf einen NULL-Wert fest: Grant-CsUserServicesPolicy-Identity "Ken Myers"-Richtliniennamen $NULL 
  
Die Terminologie "verhindert, dass Ken-Kontakte in den einheitlichen Kontaktspeicher migriert werden" ist wichtig, wenn Sie mit dem Unified Contact Store arbeiten. Wenn Sie einfach Ken eine neue Richtlinie für Benutzer Dienste zuweisen, werden die Kontakte nicht aus dem Unified Contact Store verschoben. Wenn sich ein Benutzer bei Skype for Business Server anmeldet, überprüft das System die Benutzer Dienste-Richtlinie des Benutzers, um festzustellen, ob seine Kontakte im Unified Contact Store aufbewahrt werden sollen. Wenn die Antwort ja lautet (das heißt, wenn die UcsAllowed-Eigenschaft auf $true festgesetzt ist), werden diese Kontakte in den Unified Contact Store migriert (vorausgesetzt, diese Kontakte sind noch nicht im Unified Contact Store). Wenn die Antwort Nein ist, ignoriert Skype for Business Server einfach die Kontakte des Benutzers und wechselt zur nächsten Aufgabe. Das bedeutet, dass Skype for Business Server die Kontakte eines Benutzers nicht automatisch aus dem Unified Contact Store verschieben wird, unabhängig vom Wert der UcsAllowed-Eigenschaft.
  
Das bedeutet auch, dass Sie nach dem Zuweisen des Benutzers zu einer neuen Richtlinie für Benutzer Dienste das Cmdlet [Invoke-CsUcsRollback](https://docs.microsoft.com/powershell/module/skype/invoke-csucsrollback?view=skype-ps) ausführen müssen, um die Kontakte des Benutzers aus dem Exchange-Server zu entfernen und zurück zu Skype for Business Server zu wechseln. Beispiel: Nachdem Sie dem Benutzer „Ken Myer“ eine neue Benutzerdienst-Richtlinie zugewiesen haben, können Sie seine Kontakte mit dem folgenden Befehl aus dem einheitlichen Kontaktspeicher verlegen:
  
```powershell
Invoke-CsUcsRollback -Identity "Ken Myer"
```

Wenn Sie die Benutzerdienst-Richtlinie ändern, ohne anschließend das Cmdlet Invoke-CsUcsRollback auszuführen, bleiben die Kontakte von Ken im einheitlichen Kontaktspeicher. Und was wäre, wenn Sie das Invoke-CsUcsRollback-Cmdlet ausführen, ohne die Benutzerdienste-Richtlinie von Ken Myer zu ändern? In diesem Fall werden die Kontakte von Ken nur vorübergehend aus dem einheitlichen Kontaktspeicher entfernt. Achten Sie hierbei bitte auf das Wort „vorübergehend“! Nachdem die Kontakte von Ken aus dem Unified Contact Store entfernt wurden, wartet Skype for Business Server 7 Tage, und überprüfen Sie dann, welche Benutzer Dienste-Richtlinie Ken zugewiesen wurde. Wenn Ken weiterhin eine Richtlinie zugewiesen ist, die ihn für den einheitlichen Kontaktspeicher aktiviert, werden seine Kontakte automatisch wieder zurück in den Kontaktspeicher verschoben. Um die Kontakte dauerhaft aus dem einheitlichen Kontaktspeicher zu entfernen, müssen Sie nicht nur das Invoke-CsUcsRollback-Cmdlet ausführen, sondern zusätzlich auch seine Benutzerdienste-Richtlinie ändern.
  
Aufgrund der zahlreichen Variablen, die sich auf die Migration auswirken können, kann schwer geschätzt werden, wie viel Zeit erforderlich ist, bis Konten vollständig zum einheitlichen Kontaktspeicher migriert sind. Als allgemeine Regel lässt sich jedoch sagen, dass die Migration nicht unmittelbar in Kraft tritt: Auch wenn Sie nur sehr wenige Kontakte migrieren, kann es zehn Minuten oder länger dauern, bis die Verschiebung abgeschlossen ist.
  

