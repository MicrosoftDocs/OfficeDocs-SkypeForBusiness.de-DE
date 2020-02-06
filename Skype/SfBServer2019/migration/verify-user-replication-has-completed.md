---
title: Überprüfen, ob die Benutzerreplikation abgeschlossen wurde
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Bei der Ausführung des Cmdlets Move-CsUser tritt möglicherweise ein Fehler auf, da die Benutzerinformationen zwischen den Active Directory-Domänendiensten (AD DS) und den Skype for Business Server 2019-Datenbanken nicht synchronisiert sind, weil die anfängliche Replikation unvollständig ist. Die Zeitdauer für den erfolgreichen Abschluss der ersten Synchronisierung des Skype for Business Server 2019-Benutzerreplikationsdiensts hängt von der Anzahl der Domänencontroller ab, die in der Active Directory-Gesamtstruktur gehostet werden, die das Skype for Business hostet. Server 2019-Pool. Der erste Synchronisierungsvorgang des Skype for Business Server 2019-Benutzerreplikationsdiensts erfolgt, wenn der Skype for Business Server 2019-Front-End-Server zum ersten Mal gestartet wird. Danach basiert die Synchronisierung auf dem Intervall des Benutzerreplikationsdiensts. Führen Sie die folgenden Schritte aus, um zu überprüfen, ob die Benutzerreplikation abgeschlossen ist, bevor Sie das Cmdlet Move-CsUser ausführen.
ms.openlocfilehash: 31f4f9f1045367e376d4536df54c32be14580312
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812653"
---
# <a name="verify-user-replication-has-completed"></a>Überprüfen, ob die Benutzerreplikation abgeschlossen wurde

Bei der Ausführung des Cmdlets **Move-CsUser** tritt möglicherweise ein Fehler auf, wenn die Benutzerinformationen zwischen den Active Directory-Domänendiensten (AD DS) und den Skype for Business Server 2019-Datenbanken nicht synchronisiert sind, weil die anfängliche Replikation unvollständig ist. Die Zeitdauer für den erfolgreichen Abschluss der ersten Synchronisierung des Skype for Business Server 2019-Benutzerreplikationsdiensts hängt von der Anzahl der Domänencontroller ab, die in der Active Directory-Gesamtstruktur gehostet werden, die das Skype for Business hostet. Server 2019-Pool. Der erste Synchronisierungsvorgang des Skype for Business Server 2019-Benutzerreplikationsdiensts erfolgt, wenn der Skype for Business Server 2019-Front-End-Server zum ersten Mal gestartet wird. Danach basiert die Synchronisierung auf dem Intervall des Benutzerreplikationsdiensts. Führen Sie die folgenden Schritte aus, um zu überprüfen, ob die Benutzerreplikation abgeschlossen ist, bevor Sie das Cmdlet **Move-CsUser** ausführen. 
  
### <a name="to-verify-that-user-replication-has-completed"></a>So überprüfen Sie, ob die Benutzerreplikation abgeschlossen ist

1. Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.
    
2. Klicken Sie auf das **Startmenü** , und klicken Sie dann auf **Ausführen**. 
    
3. Geben Sie **eventvwr. exe**ein, und klicken Sie dann auf **OK**.
    
4. Klicken Sie in der Ereignisanzeige auf **Anwendungen und Dienstprotokolle** , um Sie zu erweitern, und wählen Sie dann Skype for Business Server aus. 
    
5. Klicken Sie im Bereich **Aktionen** auf **Aktuelles Protokoll filtern**.
    
6. Klicken Sie in der Liste **Ereignisquellen** auf **ls-Benutzer Replikations**Dienst.
    
7. Geben Sie in ** \<alle\>Ereignis-IDs** **30024**ein, und klicken Sie dann auf **OK**. 
    
8. Suchen Sie in der Liste Gefilterte Ereignisse auf der Registerkarte **Allgemein** nach einem Eintrag, der besagt, dass die Benutzerreplikation erfolgreich abgeschlossen wurde. 
    

