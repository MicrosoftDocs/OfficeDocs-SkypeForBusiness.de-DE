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
localization_priority: Normal
description: Beim Ausführen des Cmdlets "CsUser" kann ein Fehler auftreten, da die Benutzerinformationen zwischen Active Directory-Domänendienste (AD DS) und den Skype for Business Server 2019-Datenbanken nicht mehr synchron sind, da die anfängliche Replikation unvollständig ist. Die Zeit bis zum erfolgreichen Abschluss der anfänglichen Synchronisierung des Skype for Business Server 2019-Benutzerreplikationsdiensts hängt von der Anzahl der Domänencontroller ab, die in der Active Directory Gesamtstruktur gehostet werden, die den Skype for Business Server 2019-Pool hostet. Der erste Synchronisierungsprozess des Skype for Business Server 2019-Benutzerreplikationsdiensts tritt auf, wenn das Skype for Business Server 2019-Front-End-Server zum ersten Mal gestartet wird. Danach wird die Synchronisierung gemäß dem Benutzerreplikationsintervall ausgeführt. Führen Sie die folgenden Schritte aus, um zu überprüfen, ob die Benutzerreplikation erfolgreich abgeschlossen wurde, bevor Sie das Cmdlet Move-CsUser ausführen.
ms.openlocfilehash: 5aa832216cc5eddce1d80cc9401ec9992c9edbf1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751647"
---
# <a name="verify-user-replication-has-completed"></a>Überprüfen, ob die Benutzerreplikation abgeschlossen wurde

Beim Ausführen des Cmdlets " **CsUser** " kann ein Fehler auftreten, wenn die Benutzerinformationen zwischen Active Directory-Domänendienste (AD DS) und den Skype for Business Server 2019-Datenbanken nicht mehr synchron sind, da die anfängliche Replikation unvollständig ist. Die Zeit bis zum erfolgreichen Abschluss der anfänglichen Synchronisierung des Skype for Business Server 2019-Benutzerreplikationsdiensts hängt von der Anzahl der Domänencontroller ab, die in der Active Directory Gesamtstruktur gehostet werden, die den Skype for Business Server 2019-Pool hostet. Der erste Synchronisierungsprozess des Skype for Business Server 2019-Benutzerreplikationsdiensts tritt auf, wenn das Skype for Business Server 2019-Front-End-Server zum ersten Mal gestartet wird. Danach basiert die Synchronisierung auf dem Benutzer Replikationsintervall. Führen Sie die folgenden Schritte aus, um zu überprüfen, ob die Benutzerreplikation abgeschlossen wurde, bevor Sie das Cmdlet " **CsUser** " ausführen. 
  
### <a name="to-verify-that-user-replication-has-completed"></a>So überprüfen Sie, dass die Benutzerreplikation abgeschlossen wurde

1. Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.
    
2. Klicken Sie auf das Menü **Start** und anschließend auf **Ausführen**. 
    
3. Geben Sie **eventvwr.exe** ein, und klicken Sie auf **OK**.
    
4. Klicken Sie in der Ereignisanzeige auf **Anwendungs-und Dienstprotokolle** , um Sie zu erweitern, und wählen Sie dann Skype for Business Server aus. 
    
5. Klicken Sie im Bereich **Aktionen** auf **Aktuelles Protokoll filtern**.
    
6. Klicken Sie in der Liste **Ereignisquellen** auf **LS User Replicator**.
    
7. **\<All Event IDs\>** Geben Sie in die **30024**ein, und klicken Sie dann auf **OK**. 
    
8. Suchen Sie in der Liste Gefilterte Ereignisse auf der Registerkarte **Allgemein** nach einem Eintrag, der besagt, dass die Benutzerreplikation erfolgreich abgeschlossen wurde. 
    

