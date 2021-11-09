---
title: Bereitstellen des SEFAUtil-Tools in Skype for Business
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: Bereitstellen des SEFAUtil-Tools in Skype for Business Server.
ms.openlocfilehash: d4d25a69476aa678f600178b9426db89670289d2
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60837327"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a>Bereitstellen des SEFAUtil-Tools in Skype for Business
 
Bereitstellen des SEFAUtil-Tools in Skype for Business Server.
  
Um die Gruppenanrufannahme bereitzustellen und zu verwalten, müssen Sie die Skype for Business Server Version des SEFAUtil-Tools verwenden. 
  
> [!IMPORTANT]
> Microsoft Unified Communications Managed API (UCMA) 5 Runtime muss auf jedem Computer installiert sein, auf dem Sie das SEFAUtil-Tool ausführen möchten. Laden Sie es hier herunter: [Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/download/details.aspx?id=47344). Sie können auch das UCMA 5 SDK herunterladen, das die Laufzeit enthält, hier: [UCMA 5.0 SDK](https://www.microsoft.com/download/details.aspx?id=47345).
  
Sie können das SEFAUtil-Tool in jedem Front-End-Pool in Ihrer Bereitstellung ausführen. Um das SEFAUtil-Tool auszuführen, müssen Sie die Schritte 1, 2 und 3 aus dem Bereitstellungs-Assistenten für Skype for Business auf dem Computer mit vertrauenswürdigen Anwendungen ausführen. SEFAUtil erfordert, dass der lokale Konfigurationsspeicher vorhanden ist, sowie ein Zertifikat.
  
> [!NOTE]
> Weitere Informationen zum Ausführen von SEFAUtil finden Sie im Blogartikel "[How to get SEFAutil running?](/archive/blogs/jenstr/how-to-get-sefautil-running)". 
  
### <a name="to-deploy-sefautil"></a>So stellen Sie SEFAUtil bereit

1. Melden Sie sich bei dem Computer an, auf dem Skype for Business Server Verwaltungsshell als Mitglied der Gruppe "RTCUniversalServerAdmins" oder mit den erforderlichen Benutzerrechten installiert ist, wie unter **"Stellvertretungs-Setupberechtigungen"** beschrieben.
    
2. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** auf **"Alle Programme",** auf **Skype for Business 2015** und dann auf **Skype for Business Server Verwaltungsshell.**
    
3. Das SEFAUtil-Tool kann nur auf einem Computer ausgeführt werden, der Teil eines vertrauenswürdigen Anwendungspools ist. Definieren Sie bei Bedarf einen vertrauenswürdigen Anwendungspool für den Front-End-Pool, in dem Sie SEFAUtil ausführen möchten. Führen Sie an der Eingabeaufforderung Folgendes aus:
    
   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > Pool-FQDN: Der FQDN des Servers oder Pools, der die SEFAUtil-Anwendung hosten wird (in der Regel ein Skype for Business Front-End-Server oder -Pool).
    > Poolregistrierungsstellen-FQDN: Der FQDN des Skype for Business Front-End-Servers oder -Pools, der diesem Anwendungspool zugeordnet ist.
    > Poolstandort: Die Standort-ID des Standorts, auf dem dieser Pool verwaltet wird.

4. Definieren Sie das SEFAUtil-Tool als vertrauenswürdige Anwendung. Führen Sie an der Eingabeaufforderung Folgendes aus:
    
   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > Bei Bedarf können Sie einen anderen Port verwenden. 
  
5. Aktivieren Sie die Topologie mit Ihren Änderungen. Führen Sie an der Eingabeaufforderung Folgendes aus:
    
   ```powershell
   Enable-CsTopology
   ```

6. Falls noch nicht geschehen, laden Sie die Skype for Business Server Version des SEFAUtil-Tools von [diesem Speicherort](https://www.microsoft.com/download/details.aspx?id=52631)herunter, und installieren Sie sie in dem vertrauenswürdigen Anwendungspool, den Sie in Schritt 3 erstellt haben.
    
7. Stellen Sie sicher, dass das SEFAUtil-Tool wie folgt ordnungsgemäß ausgeführt wird: 
    
    a. Führen Sie das Tool über die Windows Eingabeaufforderung mit Administratorrechten aus, um die Anrufweiterleitungseinstellungen eines Benutzers in Ihrer Bereitstellung anzuzeigen.
    
    b. Zeigt die Anrufweiterleitungseinstellungen eines Benutzers an. Führen Sie an der Eingabeaufforderung Folgendes aus:
    
   ```console
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

Die Anrufweiterleitungseinstellungen für den Benutzer werden angezeigt.
