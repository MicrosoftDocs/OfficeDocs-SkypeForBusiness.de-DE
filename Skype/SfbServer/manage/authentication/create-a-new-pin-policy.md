---
title: Erstellen Sie eine neue PIN-Richtlinie in Skype für Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8bdf0478-fe9f-4371-93ff-db39381a25db
description: 'Zusammenfassung: Erstellen einer neuen PIN-Richtlinie in Skype für Business Server.'
ms.openlocfilehash: ac51f0c81630969ec50494914e92c8302fa7d0aa
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879525"
---
# <a name="create-a-new-pin-policy-in-skype-for-business-server"></a>Erstellen Sie eine neue PIN-Richtlinie in Skype für Business Server
 
**Zusammenfassung:** Erstellen Sie eine neue PIN-Richtlinie in Skype für Business Server.
  
Die Seite **PIN-Richtlinie** können Sie die Nummer persönliche Identifikationsnummer (PIN)-Authentifizierung für Benutzer bereit, die eine Verbindung Skype für Unternehmen mit IP-Telefonen herstellen. Stellen Sie zur Verwendung der PIN-Authentifizierung sicher, dass in den Webdiensteinstellungen die Option **PIN-Authentifizierung aktivieren** ausgewählt ist.
  
Führen Sie die folgenden Schritte aus, um eine PIN-Richtlinie auf Benutzer- oder Standortebene zu erstellen. 
  
### <a name="to-create-a-user-or-site-pin-policy"></a>So erstellen Sie eine PIN-Richtlinie auf Benutzer- oder Standortebene

1.  Von einem Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins (oder gleichwertige Benutzerrechte verfügt), oder der CsServerAdministrator oder CsAdministrator-Rolle, melden Sie sich an einem beliebigen Computer, die im Netzwerk ist in der Bereitstellung von Skype für Business Server zugeordnet ist .
    
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 
    
3. Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **PIN-Richtlinie**.
    
4. Klicken Sie auf der Seite **PIN-Richtlinie** auf **Neu** und führen Sie eine der folgenden Aktionen aus:
    
   - Klicken Sie auf **Hinzufügen**, um eine Richtlinie auf Benutzerebene zu erstellen. Geben Sie im Abschnitt **Neue PIN-Richtlinie** in **Name** einen beschreibenden Namen für die Richtlinie ein.
    
   - Klicken Sie auf **Standortrichtlinie**, um eine Richtlinie auf Standortebene zu erstellen. Geben Sie im Suchfeld **Standort auswählen** den vollständigen oder teilweisen Namen des Standorts ein, für den Sie eine Richtlinie erstellen möchten. Klicken Sie in der Liste der Standorte auf den gewünschten Standort und dann auf **OK**.
    
5. Geben Sie im Feld **Beschreibung** eine Beschreibung für die PIN-Richtlinie ein.
    
6. Geben Sie im Feld **PIN-Mindestlänge** die gewünschte Mindestlänge für die PIN ein oder wählen Sie sie aus. In der Standardeinstellung beträgt die Mindestlänge fünf Ziffern.
    
7. Aktivieren Sie das Kontrollkästchen **Maximale Anzahl von Anmeldeversuchen angeben**, um anzugeben, nach wie vielen erfolglosen Anmeldeversuchen ein Benutzer gesperrt wird. Wenn Sie diese Option nicht aktivieren, wird die maximale Anzahl von Anmeldeversuchen basierend auf der PIN-Länge automatisch festgelegt. In der Standardeinstellung wird die maximale Anzahl von Anmeldeversuchen automatisch festgelegt.
    
8. Wenn Sie das Kontrollkästchen **Maximale Anzahl von Anmeldeversuchen angeben** aktiviert haben, geben Sie in **Maximale Anzahl von Anmeldeversuchen** die maximale Anzahl von Anmeldeversuchen ein, die Sie zulassen möchten. Sie können auch einen Wert auswählen.
    
9. Aktivieren Sie das Kontrollkästchen **PIN-Ablauf aktivieren**, um eine PIN-Ablaufdauer festzulegen. Wenn Sie diese Option nicht aktivieren, laufen PINs nie ab. In der Standardeinstellung ist für PINs kein Ablauf festgelegt.
    
10. Wenn Sie das Kontrollkästchen **PIN-Ablauf aktivieren** aktiviert haben, geben Sie unter **PIN-Ablauf nach (Tagen)** die Anzahl von Tagen ein, nach der PINs ablaufen.
    
11. Geben Sie unter **PIN-Verlaufszähler** die Anzahl von PINs ein, die ein Benutzer erstellen muss, bevor eine PIN erneut verwendet werden kann. In der Standardeinstellung können Benutzer ihre PINs erneut verwenden.
    
12. Aktivieren Sie das Kontrollkästchen **Allgemeine Muster zulassen**, um allgemeine Muster wie „1234“ und „8888“ in PINs zuzulassen. Wenn Sie diese Option nicht aktivieren, sind nur komplexe Ziffernmuster zulässig. In der Standardeinstellung dürfen nur komplexe Ziffernmuster verwendet werden.
    
    > [!IMPORTANT]
    > Es wird empfohlen, die Verwendung gängiger Muster nicht zuzulassen. 
  
13. Klicken Sie auf **Commit ausführen**.
    

