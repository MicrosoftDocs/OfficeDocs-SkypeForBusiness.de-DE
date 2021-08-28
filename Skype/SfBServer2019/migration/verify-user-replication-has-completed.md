---
title: Überprüfen, ob die Benutzerreplikation abgeschlossen wurde
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Beim Ausführen des Cmdlets Move-CsUser tritt möglicherweise ein Fehler auf, da Benutzerinformationen zwischen Active Directory Domain Services (AD DS) und den Skype for Business Server 2019-Datenbanken nicht synchronisiert werden, da die anfängliche Replikation unvollständig ist. Die Zeit, die für den erfolgreichen Abschluss der ersten Synchronisierung des Skype for Business Server 2019-Benutzerreplikationsdiensts benötigt wird, hängt von der Anzahl der Domänencontroller ab, die in der Active Directory-Gesamtstruktur gehostet werden, die den pool Skype for Business Server 2019 hostet. Der erste Synchronisierungsprozess des Skype for Business Server 2019-Benutzerreplikationsdiensts findet statt, wenn der Front-End-Server Skype for Business Server 2019 zum ersten Mal gestartet wird. Danach wird die Synchronisierung gemäß dem Benutzerreplikationsintervall ausgeführt. Führen Sie die folgenden Schritte aus, um zu überprüfen, ob die Benutzerreplikation erfolgreich abgeschlossen wurde, bevor Sie das Cmdlet Move-CsUser ausführen.
ms.openlocfilehash: 893702b18b376edc32e946998aeead122bf3ed68
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58599700"
---
# <a name="verify-user-replication-has-completed"></a>Überprüfen, ob die Benutzerreplikation abgeschlossen wurde

Beim Ausführen des **Cmdlets "Move-CsUser"** tritt möglicherweise ein Fehler auf, wenn Benutzerinformationen zwischen Active Directory Domain Services (AD DS) und den Skype for Business Server 2019-Datenbanken nicht synchronisiert werden, da die anfängliche Replikation unvollständig ist. Die Zeit, die für den erfolgreichen Abschluss der ersten Synchronisierung des Skype for Business Server 2019-Benutzerreplikationsdiensts benötigt wird, hängt von der Anzahl der Domänencontroller ab, die in der Active Directory-Gesamtstruktur gehostet werden, die den pool Skype for Business Server 2019 hostet. Der erste Synchronisierungsprozess des Skype for Business Server 2019-Benutzerreplikationsdiensts findet statt, wenn der Front-End-Server Skype for Business Server 2019 zum ersten Mal gestartet wird. Danach basiert die Synchronisierung auf dem Intervall des Benutzerreplikationsdiensts. Führen Sie die folgenden Schritte aus, um zu überprüfen, ob die Benutzerreplikation abgeschlossen wurde, bevor Sie das **Cmdlet "Move-CsUser"** ausführen. 
  
### <a name="to-verify-that-user-replication-has-completed"></a>So überprüfen Sie, dass die Benutzerreplikation abgeschlossen wurde

1. Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.
    
2. Klicken Sie auf das Menü **Start** und anschließend auf **Ausführen**. 
    
3. Geben Sie **eventvwr.exe** ein, und klicken Sie auf **OK**.
    
4. Klicken Sie in der Ereignisanzeige auf **Anwendungs- und Dienstprotokolle,** um sie zu erweitern, und wählen Sie dann Skype for Business Server aus. 
    
5. Klicken Sie im Bereich **Aktionen** auf **Aktuelles Protokoll filtern**.
    
6. Klicken Sie in der Liste **Ereignisquellen** auf **LS User Replicator**.
    
7. **\<All Event IDs\>** Geben Sie in **30024** ein, und klicken Sie dann auf **OK.** 
    
8. Suchen Sie in der Liste gefilterter Ereignisse auf der Registerkarte **"Allgemein"** nach einem Eintrag, der angibt, dass die Benutzerreplikation erfolgreich abgeschlossen wurde. 
    

