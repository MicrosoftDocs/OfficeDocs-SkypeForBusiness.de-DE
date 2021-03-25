---
title: Bereitstellen des SEFAUtil-Tools in Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 013890e3b65dfd3a8360da859a1c9179fa9b5a13
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105801"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a>Bereitstellen des SEFAUtil-Tools in Skype for Business
 
Bereitstellen des SEFAUtil-Tools in Skype for Business Server.
  
Zum Bereitstellen und Verwalten der Gruppenanrufannahme müssen Sie die Skype for Business Server-Version des SEFAUtil-Tools verwenden. 
  
> [!IMPORTANT]
> Microsoft Unified Communications Managed API (UCMA) 5 Runtime muss auf jedem Computer installiert sein, auf dem Sie das SEFAUtil-Tool ausführen möchten. Laden Sie es hier herunter: [Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/download/details.aspx?id=47344). Sie können auch das UCMA 5 SDK herunterladen, das die Laufzeit enthält, hier: [UCMA 5.0 SDK](https://www.microsoft.com/download/details.aspx?id=47345).
  
Sie können das SEFAUtil-Tool in einem beliebigen Front-End-Pool in Ihrer Bereitstellung ausführen. Zum Ausführen des SEFAUtil-Tools müssen Sie die Schritte 1, 2 und 3 im Skype for Business-Bereitstellungs-Assistenten auf dem vertrauenswürdigen Anwendungscomputer ausführen. FÜR SEFAUtil muss der lokale Konfigurationsspeicher sowie ein Zertifikat vorhanden sein.
  
> [!NOTE]
> Weitere Informationen zum Ausführen von SEFAUtil finden Sie im Blogartikel "[How to get SEFAutil running?](/archive/blogs/jenstr/how-to-get-sefautil-running)". 
  
### <a name="to-deploy-sefautil"></a>So stellen Sie SEFAUtil

1. Melden Sie sich an dem Computer an, auf dem Skype for Business Server Management Shell als Mitglied der Gruppe RTCUniversalServerAdmins installiert ist, oder mit den erforderlichen Benutzerrechten, wie unter **Delegate Setup Permissions beschrieben.**
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start,** klicken Sie auf **Alle Programme,** **klicken Sie auf Skype for Business 2015,** und klicken Sie dann auf **Skype for Business Server Management Shell**.
    
3. Das SEFAUtil-Tool kann nur auf einem Computer ausgeführt werden, der Teil eines vertrauenswürdigen Anwendungspools ist. Definieren Sie bei Bedarf einen vertrauenswürdigen Anwendungspool für den Front-End-Pool, in dem Sie SEFAUtil ausführen möchten. Führen Sie an der Eingabeaufforderung Folgendes aus:
    
   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > Pool-FQDN: Der FQDN des Servers oder Pools, der die SEFAUtil-Anwendung hostet (in der Regel ein Skype for Business-Front-End-Server oder -Pool).
    > FQDN der Poolregistrierungsstelle: Der FQDN des Skype for Business-Front-End-Servers oder -Pools, der diesem Anwendungspool zugeordnet ist.
    > Poolwebsite: Die Standort-ID des Standorts, auf dem dieser Pool befindet.

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

6. Falls noch nicht, laden Sie die Skype for Business Server-Version des SEFAUtil-Tools von diesem Speicherort [herunter,](https://www.microsoft.com/download/details.aspx?id=52631)und installieren Sie sie im vertrauenswürdigen Anwendungspool, den Sie in Schritt 3 erstellt haben.
    
7. Stellen Sie sicher, dass das SEFAUtil-Tool wie folgt ordnungsgemäß ausgeführt wird: 
    
    a. Führen Sie das Tool über die Windows-Eingabeaufforderung mit Administratorrechten aus, um die Anruf weiterleitungseinstellungen eines Benutzers in Ihrer Bereitstellung anzeigen zu können.
    
    b. Anzeigen der Anruf weiterleitungseinstellungen eines Benutzers. Führen Sie an der Eingabeaufforderung Folgendes aus:
    
   ```console
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

Die Einstellungen für die Anruf weiterleitung für den Benutzer werden angezeigt.
