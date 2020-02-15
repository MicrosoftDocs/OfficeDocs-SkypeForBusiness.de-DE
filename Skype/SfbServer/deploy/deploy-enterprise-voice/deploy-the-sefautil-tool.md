---
title: Bereitstellen des SEFAUtil-Tools in Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: Bereitstellen des SEFAUtil-Tools in Skype for Business Server.
ms.openlocfilehash: 306e2ec305e9e12cd3486691b3e239e2aedfb548
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "41986810"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a>Bereitstellen des SEFAUtil-Tools in Skype for Business
 
Bereitstellen des SEFAUtil-Tools in Skype for Business Server.
  
Zum Bereitstellen und Verwalten der gruppenanrufannahme müssen Sie die Skype for Business Server Version des SEFAUtil-Tools verwenden. 
  
> [!IMPORTANT]
> Verwaltete API von Microsoft Unified Communications (UCMA) 5-Laufzeitmodul muss auf jedem Computer installiert sein, auf dem Sie das SEFAUtil-Tool ausführen möchten. Laden Sie ihn hier herunter: [Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/download/details.aspx?id=47344). Sie können auch das UCMA 5 SDK, das die Laufzeit enthält, hier herunterladen: [SDK für UCMA 5.0](https://www.microsoft.com/download/details.aspx?id=47345).
  
Sie können das SEFAUtil-Tool in jeder Front-End-Pool in Ihrer Bereitstellung ausführen. Zum Ausführen des SEFAUtil-Tools müssen Sie die Schritte 1, 2 und 3 im Skype for Business-Bereitstellungs-Assistenten auf dem Computer mit vertrauenswürdigen Anwendungen ausführen. SEFAUtil erfordert, dass der lokale Konfigurationsspeicher vorhanden ist, sowie ein Zertifikat.
  
> [!NOTE]
> Weitere Informationen zur Ausführung von SEFAUtil finden Sie im Blog-Artikel "[How to Get SEFAUtil Running?](https://go.microsoft.com/fwlink/?LinkId=278940)". 
  
### <a name="to-deploy-sefautil"></a>So stellen Sie SEFAUtil bereit

1. Melden Sie sich an dem Computer an, auf dem Skype for Business Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder mit den erforderlichen Benutzerrechten installiert ist, wie unter **Delegieren von Setup Berechtigungen**beschrieben.
    
2. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for Business 2015**, und klicken Sie dann auf **Skype for Business Server Management Shell**.
    
3. Das SEFAUtil-Tool kann nur auf einem Computer ausgeführt werden, der Teil eines vertrauenswürdigen Anwendungspools ist. Definieren Sie bei Bedarf einen vertrauenswürdigen Anwendungspool für die Front-End-Pool, in der Sie SEFAUtil ausführen möchten. Führen Sie an der Eingabeaufforderung Folgendes aus:
    
   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > Pool-FQDN: der FQDN des Servers oder Pools, der als Host für die SEFAUtil-Anwendung verwendet wird (in der Regel ein Skype for Business-Front-End-Server oder-Pool).
    > FQDN des Pool Registrierungsstelle: der FQDN des Skype for Business Front-End-Servers oder Pools, der diesem Anwendungspool zugeordnet ist.
    > Pool Website: die Website-ID der Website, auf der dieser Pool verwaltet wird.

4. Definieren Sie das SEFAUtil-Tool als vertrauenswürdige Anwendung. Führen Sie an der Eingabeaufforderung Folgendes aus:
    
   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > Sie können bei Bedarf einen anderen Port verwenden. 
  
5. Aktivieren Sie die Topologie mit Ihren Änderungen. Führen Sie an der Eingabeaufforderung Folgendes aus:
    
   ```powershell
   Enable-CsTopology
   ```

6. Wenn Sie noch nicht vorhanden sind, laden Sie die Skype for Business Server Version des SEFAUtil-Tools von [diesem Speicherort](https://www.microsoft.com/download/details.aspx?id=52631)herunter, und installieren Sie Sie in dem vertrauenswürdigen Anwendungspool, den Sie in Schritt 3 erstellt haben.
    
7. Stellen Sie sicher, dass das SEFAUtil-Tool wie folgt ordnungsgemäß ausgeführt wird: 
    
    a. Führen Sie das Tool über die Windows-Eingabeaufforderung mit Administratorrechten aus, um die Anrufweiterleitungseinstellungen eines Benutzers in Ihrer Bereitstellung anzuzeigen.
    
    b. Zeigt die Anrufweiterleitungseinstellungen eines Benutzers an. Führen Sie an der Eingabeaufforderung Folgendes aus:
    
   ```console
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

Die Anrufweiterleitungseinstellungen für den Benutzer werden angezeigt.
    

