---
title: Das Tool SEFAUtil in Skype für Unternehmen bereitstellen
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: Bereitstellen von dem Tool SEFAUtil in Skype für Business Server ein.
ms.openlocfilehash: 55079f1727a6671a41e87582edd5810a4daa731f
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "21001203"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a>Das Tool SEFAUtil in Skype für Unternehmen bereitstellen
 
Bereitstellen von dem Tool SEFAUtil in Skype für Business Server ein.
  
Zum Bereitstellen und Verwalten der Gruppe anrufen Pickup-, müssen Sie die Skype für Business Server-Version des Tools SEFAUtil verwenden. 
  
> [!IMPORTANT]
> Microsoft Unified Communications Managed API (UCMA) 5 Runtime muss auf jedem Computer installiert sein, auf dem Sie das Tool SEFAUtil ausführen möchten. Hier herunterladen: [Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/en-us/download/details.aspx?id=47344). Sie können auch die UCMA 5-SDK, einschließlich die Laufzeit hier herunterladen: [UCMA 5.0 SDK](https://www.microsoft.com/en-us/download/details.aspx?id=47345).
  
Sie können das Tool SEFAUtil in Ihrer Bereitstellung in einem beliebigen Front-End-Pool ausführen. Zum Ausführen des Tools SEFAUtil müssen Sie die Schritte 1, 2 und 3 aus der Skype für Business Bereitstellungs-Assistenten auf dem Computer für die vertrauenswürdige Anwendung ausführen. SEFAUtil ist der lokale Konfigurationsspeicher vorhanden sein muss, sowie ein Zertifikat erforderlich.
  
> [!NOTE]
> Weitere Informationen zum Ausführen von SEFAUtil, finden Sie im Blog-Artikel "[SEFAutil unter Abrufen von?](https://go.microsoft.com/fwlink/?LinkId=278940)". 
  
### <a name="to-deploy-sefautil"></a>So stellen Sie das SEFAUtil-Tool bereit

1. Melden Sie sich an dem Computer, auf dem Skype für Business Server-Verwaltungsshell, als Mitglied der Gruppe RTCUniversalServerAdmins oder mit den erforderlichen Benutzerrechten installiert ist wie beschrieben unter **Delegate Setup Permissions**.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
3. Das SEFAUtil-Tool kann nur auf einem Computer ausgeführt werden, der zu einem vertrauenswürdigen Anwendungspool gehört. Definieren Sie bei Bedarf einen vertrauenswürdigen Anwendungspool für den Front-End-Pool, SEFAUtil ausgeführt werden soll. Führen Sie an der Eingabeaufforderung folgenden Befehl aus:
    
   ```
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

4. Definieren Sie das SEFAUtil-Tool als eine vertrauenswürdige Anwendung. Führen Sie an der Eingabeaufforderung folgenden Befehl aus:
    
   ```
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > Sie können ggf. einen anderen Port verwenden. 
  
5. Aktivieren Sie die Topologie mit Ihren Änderungen. Führen Sie an der Eingabeaufforderung folgenden Befehl aus:
    
  ```
  Enable-CsTopology
  ```

6. Wenn Sie noch nicht geschehen ist, laden Sie die Skype für Business Server-Version des Tools SEFAUtil aus [diesem Speicherort](https://www.microsoft.com/en-us/download/details.aspx?id=52631), und installieren Sie es auf den vertrauenswürdigen Anwendungspool in Schritt 3 erstellte.
    
7. Gehen Sie wie folgt vor, um sicherzustellen, dass Ihr SEFAUtil-Tool korrekt ausgeführt wird: 
    
    a. Führen Sie das Tool an der Windows-Eingabeaufforderung mit Administratorberechtigungen aus, um die Anrufweiterleistungseinstellungen eines Benutzers in Ihrer Bereitstellung anzuzeigen.
    
    b. Zeigen Sie die Anrufweiterleitungseinstellungen eines Benutzers an. Führen Sie an der Eingabeaufforderung folgenden Befehl aus:
    
  ```
  SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
  ```

Die Anrufweiterleitungseinstellungen für den Benutzer werden angezeigt.
    

