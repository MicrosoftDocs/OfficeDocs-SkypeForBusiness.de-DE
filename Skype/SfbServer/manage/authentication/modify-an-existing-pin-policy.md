---
title: Ändern einer vorhandenen PIN-Richtlinie in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 517caaee-3349-4fa6-8d86-e4da3258a445
description: 'Zusammenfassung: Ändern einer vorhandenen PIN-Richtlinie in Skype for Business Server.'
ms.openlocfilehash: 7770e34315dc0e407ecc4523fc133fce696d9c5b5eadba35979937761230b0cf
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54297341"
---
# <a name="modify-an-existing-pin-policy-in-skype-for-business-server"></a>Ändern einer vorhandenen PIN-Richtlinie in Skype for Business Server
 
**Zusammenfassung:** Ändern einer vorhandenen PIN-Richtlinie in Skype for Business Server.
  
Sie können die Registerkarte **"PIN-Richtlinie"** verwenden, um Benutzern, die eine Verbindung mit Skype for Business mit IP-Telefonen herstellen, eine PIN-Authentifizierung (Persönliche Identifikationsnummer) bereitzustellen. Stellen Sie zur Verwendung der PIN-Authentifizierung sicher, dass in den Webdiensteinstellungen die Option **PIN-Authentifizierung aktivieren** ausgewählt ist.
  
Führen Sie die folgenden Schritte aus, um eine PIN-Richtlinie auf Benutzer- oder Standortebene zu ändern. 
  
### <a name="to-modify-an-existing-pin-policy"></a>So ändern Sie eine vorhandene PIN-Richtlinie

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsServerAdministrator" oder "CsAdministrator" zugewiesen ist, bei jedem Computer an, der sich im Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen. 
    
3. Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **PIN-Richtlinie**.
    
4. Klicken Sie auf der Seite **PIN-Richtlinie** auf eine Richtlinie, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.
    
5. Geben Sie unter **PIN-Richtlinie bearbeiten** im Feld **PIN-Mindestlänge** die gewünschte Mindestlänge für die PIN ein, oder wählen Sie sie aus. In der Standardeinstellung beträgt die Mindestlänge fünf Ziffern.
    
6. Aktivieren Sie das Kontrollkästchen **Maximale Anmeldeversuche angeben**, um anzugeben, nach wie vielen erfolglosen Anmeldeversuchen ein Benutzer gesperrt wird. Wenn Sie diese Option nicht aktivieren, wird die maximale Anzahl von Anmeldeversuchen basierend auf der PIN-Länge automatisch festgelegt. In der Standardeinstellung wird die maximale Anzahl von Anmeldeversuchen automatisch festgelegt.
    
7. Wenn Sie das Kontrollkästchen **Maximale Anzahl von Anmeldeversuchen angeben** aktiviert haben, geben Sie in **Maximale Anzahl von Anmeldeversuchen** die maximale Anzahl von Anmeldeversuchen ein, die Sie zulassen möchten. Sie können auch einen Wert auswählen.
    
8. Aktivieren Sie das Kontrollkästchen **PIN-Ablauf aktivieren**, um eine PIN-Ablaufdauer festzulegen. Wenn Sie diese Option nicht aktivieren, laufen PINs nie ab. In der Standardeinstellung ist für PINs kein Ablauf festgelegt.
    
9. Wenn Sie das Kontrollkästchen **PIN-Ablauf aktivieren** aktiviert haben, geben Sie unter **PIN-Ablauf nach (Tagen)** die Anzahl von Tagen ein, nach der PINs ablaufen.
    
10. Geben Sie unter **PIN-Verlaufszähler** die Anzahl von PINs ein, die ein Benutzer erstellen muss, bevor eine PIN erneut verwendet werden kann. In der Standardeinstellung können Benutzer ihre PINs erneut verwenden.
    
11. Aktivieren Sie das Kontrollkästchen **Allgemeine Muster zulassen**, um allgemeine Muster in PINs zuzulassen, beispielsweise aufeinanderfolgende und wiederholte Zahlen. Wenn Sie diese Option nicht aktivieren, sind nur komplexe Ziffernmuster zulässig. In der Standardeinstellung dürfen nur komplexe Ziffernmuster verwendet werden.
    
    > [!IMPORTANT]
    > Es wird empfohlen, die Verwendung gängiger Muster nicht zuzulassen. 
  
12. Klicken Sie auf **Commit ausführen**.
    

