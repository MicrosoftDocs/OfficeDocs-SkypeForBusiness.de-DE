---
title: Vorbereiten der aktuellen Gesamtstruktur
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11f5e359-97eb-45f7-a730-9ddbbaa40b83
ROBOTS: NOINDEX, NOFOLLOW
description: Zum Vorbereiten der Active Directory-Domänendienste-Gesamtstruktur müssen Sie erfolgreich das Schema erweitern (Siehe im Thema Running Schema Preparation), und stellen Sie sicher, dass das Schema repliziert wurde.
ms.openlocfilehash: 8bab8fecef4980c2d82f92a90f5c11c6bf7870f1
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20971897"
---
# <a name="prepare-current-forest"></a>Vorbereiten der aktuellen Gesamtstruktur
 
Zum Vorbereiten der Active Directory-Domänendienste-Gesamtstruktur müssen Sie erfolgreich das Schema erweitern (Siehe im Thema [Running Schema Preparation](http://technet.microsoft.com/library/067726ae-fd3f-4133-a32f-26d2603ac674.aspx)), und stellen Sie sicher, dass das Schema repliziert wurde.
  
Sobald diese Voraussetzungen erfüllt sind, können Sie mit **Schritt 3: Aktuelle Gesamtstruktur vorbereiten** beginnen. Melden Sie sich zum Vorbereiten der Gesamtstruktur bei einem Computer in der Stammdomäne der Gesamtstruktur als Mitglied der Gruppe „Domänen-Admins“ in der Stammdomäne der Gesamtstruktur oder der Gruppe „Organisations-Admins“ für die Gesamtstruktur an, die Sie vorbereiten.
  
1. Klicken Sie im Bereitstellungs-Assistenten unter **Schritt 3: Vorbereiten der aktuellen Gesamtstruktur** auf **Ausführen**.
    
2. Klicken Sie auf der Seite **Vorbereiten der aktuellen Gesamtstruktur** auf **Weiter**.
    
    > [!NOTE]
    > Vorbereitung der Gesamtstruktur können Sie wählen, wo die universellen Gruppen für Skype für Business Server platziert. Wählen Sie einen Speicherort entsprechend den Anforderungen Ihrer Organisation. 
  
3. Suchen Sie auf der Seite **Befehle ausführen** nach **Aufgabenstatus: Abgeschlossen** und klicken Sie dann auf **Protokoll anzeigen**. Vergewissern Sie sich, dass keine Fehler vorliegen. Überprüfen Sie die Warnungen dahingehend, ob sie erwartet werden und für Ihre Infrastruktur typisch sind.
    
4. Erweitern Sie unter der Spalte **Aktion** im Protokoll **Der Vorbereitung der Gesamtstruktur**, suchen Sie nach einer ** \<Erfolg\> ** Ausführungsergebnis am Ende jeder Aufgabe zu prüfen, Vorbereitung der Gesamtstruktur erfolgreich abgeschlossen wurde, schließen Sie das Protokoll und klicken Sie dann auf Fertig stellen ** **.
    
5. Warten Sie Active Directory-Domänendienste-Replikation abgeschlossen ist, oder erzwingen Sie die Replikation auf allen Domänencontrollern in der **Active Directory-Standorte und -Dienste** -Snap-in für den Domänencontroller des Gesamtstrukturstamms, vor dem Ausführen der domänenvorbereitung aufgeführt. Erzwingen Sie die Replikation zwischen den Domänencontrollern an allen Active Directory-Standorte, die dazu führen, dass die Replikation an den Standorten innerhalb von Minuten durchgeführt.
    
    > [!TIP]
    > Wenn Sie die Protokolldateien überprüfen, die durch die Skype für Business Server-Bereitstellungs-Assistenten erstellt werden müssen, können sie auf dem Computer finden Sie dem Bereitstellungs-Assistenten ausgeführt wurde, in das Verzeichnis Benutzer des Benutzers Active Directory Domain Services, die im Schritt ausgeführt hat. Angenommen, wenn der Benutzer als Domänenadministrator in der Domäne Contoso.net angemeldet, die Protokolldateien befinden sich im: C:\Users\Administrator.Contoso\AppData\Local\Temp 
  

