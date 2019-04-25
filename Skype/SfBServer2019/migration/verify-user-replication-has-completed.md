---
title: Überprüfen, ob die Benutzerreplikation abgeschlossen wurde
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Wenn Sie das Move-CsUser-Cmdlet ausführen, auftreten einen Fehler, da die Benutzerinformationen zwischen Active Directory-Domänendienste (AD DS) und der Skype für Business Server 2019 Datenbanken sind nicht synchronisiert, da die Erstreplikation unvollständig ist. Der Zeitaufwand für die erfolgreiche der Skype für die anfängliche Synchronisierung des Dienstes Business Server 2019 Benutzerreplikationsdienst hängt von der Anzahl der Domänencontroller, die in der Active Directory-Gesamtstruktur gehostet werden, die die Skype für Unternehmen gehostet wird. Server 2019 Pool. Die Skype für Business Server 2019 Benutzerreplikationsdienst Service erstsynchronisierung Prozess tritt auf, wenn die Skype für Business Server 2019 Front-End-Server zum ersten Mal gestartet wird. Nach Ausführung dieses basiert die Synchronisierung klicken Sie dann auf das Intervall für den Benutzerreplikationsdienst. Führen Sie die folgenden Schritte aus, um sicherzustellen, dass die Benutzerreplikation abgeschlossen ist, bevor Sie das Move-CsUser-Cmdlet ausführen.
ms.openlocfilehash: bab54e91ebda7a10804980e368e05bb58ff911ff
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231336"
---
# <a name="verify-user-replication-has-completed"></a>Überprüfen, ob die Benutzerreplikation abgeschlossen wurde

Wenn Sie das **Move-CsUser** -Cmdlet ausführen zu können, kann einen Fehler auftreten, wenn Benutzerinformationen zwischen Active Directory-Domänendienste (AD DS) und der Skype für Business Server 2019 Datenbanken nicht synchronisiert sind, da die Erstreplikation unvollständig ist. Der Zeitaufwand für die erfolgreiche der Skype für die anfängliche Synchronisierung des Dienstes Business Server 2019 Benutzerreplikationsdienst hängt von der Anzahl der Domänencontroller, die in der Active Directory-Gesamtstruktur gehostet werden, die die Skype für Unternehmen gehostet wird. Server 2019 Pool. Die Skype für Business Server 2019 Benutzerreplikationsdienst Service erstsynchronisierung Prozess tritt auf, wenn die Skype für Business Server 2019 Front-End-Server zum ersten Mal gestartet wird. Nach Ausführung dieses basiert die Synchronisierung auf das Intervall für den Benutzerreplikationsdienst. Führen Sie die folgenden Schritte aus, um sicherzustellen, dass die Benutzerreplikation abgeschlossen ist, vor dem Ausführen des Cmdlets **Move-CsUser** . 
  
### <a name="to-verify-that-user-replication-has-completed"></a>So überprüfen Sie, dass die Benutzerreplikation abgeschlossen hat

1. Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.
    
2. Klicken Sie auf **das Startmenü** , und klicken Sie dann auf **Ausführen**. 
    
3. Geben Sie **eventvwr.exe**ein, und klicken Sie dann auf **OK**.
    
4. Klicken Sie in der Ereignisanzeige auf **Anwendungs- und Dienstprotokolle,** um ihn zu erweitern, und wählen Sie dann Skype für Business Server aus. 
    
5. Klicken Sie im Bereich **Aktionen** auf **Aktuelles Protokoll filtern**.
    
6. Klicken Sie in der Liste **Ereignisquellen** auf **LS User Replicator**.
    
7. In ** \<alle Ereignis-IDs\>**, geben Sie **den Wert 30024 ein**, und klicken Sie dann auf **OK**. 
    
8. Suchen Sie in der gefilterten Ereignisliste auf der Registerkarte **Allgemein** nach einem Eintrag, der besagt, dass die Benutzerreplikation erfolgreich abgeschlossen wurde. 
    

