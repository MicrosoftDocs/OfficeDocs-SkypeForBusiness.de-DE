---
title: Bereitstellen des Tools SEFAUtil in Skype for Business
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
description: Bereitstellen des Tools SEFAUtil in Skype for Business Server.
ms.openlocfilehash: 20cda161c182c8dfb426f61b793366b7f60f37d5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812385"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a>Bereitstellen des Tools SEFAUtil in Skype for Business
 
Bereitstellen des Tools SEFAUtil in Skype for Business Server.
  
Zum Bereitstellen und Verwalten der Gruppenanrufannahme müssen Sie die Skype for Business Server-Version des SEFAUtil-Tools verwenden. 
  
> [!IMPORTANT]
> Die Microsoft Unified Communications Managed API (UCMA) 5 Runtime muss auf jedem Computer installiert sein, auf dem Sie das Tool SEFAUtil ausführen möchten. Laden Sie es hier herunter: [Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/download/details.aspx?id=47344). Sie können auch das UCMA 5 SDK herunterladen, das die Laufzeit enthält: [UCMA 5.0 SDK](https://www.microsoft.com/download/details.aspx?id=47345).
  
Sie können das Tool SEFAUtil in einem beliebigen Front-End-Pool in Ihrer Bereitstellung ausführen. Um das Tool SEFAUtil ausführen zu können, müssen Sie die Schritte 1, 2 und 3 im Skype for Business-Bereitstellungs-Assistenten auf dem Computer mit vertrauenswürdigen Anwendungen ausführen. SEFAUtil erfordert, dass der lokale Konfigurationsspeicher vorhanden ist, sowie ein Zertifikat.
  
> [!NOTE]
> Weitere Informationen zum Ausführen von SEFAUtil finden Sie im Blogartikel["How to get SEFAutil running?](https://go.microsoft.com/fwlink/?LinkId=278940)". 
  
### <a name="to-deploy-sefautil"></a>So stellen Sie SEFAUtil

1. Melden Sie sich bei dem Computer, auf dem Skype for Business Server Management Shell installiert ist, als Mitglied der Gruppe "RTCUniversalServerAdmins" oder mit den erforderlichen Benutzerrechten an, wie unter "Berechtigungen zum Delegieren des **Setups" beschrieben.**
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **"Start",**"Alle **Programme",** **"Skype for Business 2015"** und dann auf **"Skype for Business Server-Verwaltungsshell".**
    
3. Das Tool SEFAUtil kann nur auf einem Computer ausgeführt werden, der Teil eines vertrauenswürdigen Anwendungspools ist. Definieren Sie bei Bedarf einen vertrauenswürdigen Anwendungspool für den Front-End-Pool, in dem Sie SEFAUtil ausführen möchten. Führen Sie an der Eingabeaufforderung Folgendes aus:
    
   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > Pool-FQDN: Der FQDN des Servers oder Pools, der die SEFAUtil-Anwendung hostet (in der Regel ein Skype for Business-Front-End-Server oder -Pool).
    > Poolregistrierungs-FQDN: Der FQDN des Skype for Business-Front-End-Servers oder -Pools, der diesem Anwendungspool zugeordnet ist.
    > Poolstandort: Die Standort-ID des Standorts, an dem dieser Pool liegt.

4. Definieren Sie das TOOL SEFAUtil als vertrauenswürdige Anwendung. Führen Sie an der Eingabeaufforderung Folgendes aus:
    
   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > Sie können bei Bedarf einen anderen Port verwenden. 
  
5. Aktivieren Sie die Topologie mit Ihren Änderungen. Führen Sie an der Eingabeaufforderung Folgendes aus:
    
   ```powershell
   Enable-CsTopology
   ```

6. Falls noch nicht, laden Sie die Skype for Business Server-Version des Tools SEFAUtil von diesem Speicherort [herunter,](https://www.microsoft.com/download/details.aspx?id=52631)und installieren Sie sie in dem vertrauenswürdigen Anwendungspool, den Sie in Schritt 3 erstellt haben.
    
7. Stellen Sie wie folgt sicher, dass das Tool SEFAUtil ordnungsgemäß ausgeführt wird: 
    
    a. Führen Sie das Tool über die Windows-Eingabeaufforderung mit Administratorrechten aus, um die Anruf weiterleitungseinstellungen eines Benutzers in Ihrer Bereitstellung anzeigen.
    
    b. Zeigt die Anruf weiterleitungseinstellungen eines Benutzers an. Führen Sie an der Eingabeaufforderung Folgendes aus:
    
   ```console
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

Die Anruf weiterleitungseinstellungen für den Benutzer werden angezeigt.
    

