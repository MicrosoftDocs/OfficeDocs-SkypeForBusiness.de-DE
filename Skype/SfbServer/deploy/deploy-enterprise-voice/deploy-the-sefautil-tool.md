---
title: Bereitstellen des SEFAUtil-Tools in Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: Bereitstellen des SEFAUtil-Tools in Skype for Business Server.
ms.openlocfilehash: e36448652f245d1c81a00cc206b6e8047a8f9d28
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001885"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a>Bereitstellen des SEFAUtil-Tools in Skype for Business
 
Bereitstellen des SEFAUtil-Tools in Skype for Business Server.
  
Zur Bereitstellung und Verwaltung der Gruppenanruf Abholung müssen Sie die Skype for Business Server-Version des SEFAUtil-Tools verwenden. 
  
> [!IMPORTANT]
> Microsoft Unified Communications Managed API (UCMA) 5 Runtime muss auf jedem Computer installiert sein, auf dem Sie das SEFAUtil-Tool ausführen möchten. Laden Sie Sie hier herunter: [Unified Communications Managed API 5,0-Laufzeit](https://www.microsoft.com/en-us/download/details.aspx?id=47344). Sie können auch das UCMA 5 SDK, das die Laufzeit enthält, hier herunterladen: [UCMA 5,0 SDK](https://www.microsoft.com/en-us/download/details.aspx?id=47345).
  
Sie können das SEFAUtil-Tool in einem beliebigen Front-End-Pool in Ihrer Bereitstellung ausführen. Um das SEFAUtil-Tool ausführen zu können, müssen Sie die Schritte 1, 2 und 3 im Skype for Business-Bereitstellungs-Assistenten auf dem vertrauenswürdigen Anwendungs Computer ausführen. SEFAUtil erfordert das vorhanden sein des lokalen Konfigurationsspeichers sowie ein Zertifikat.
  
> [!NOTE]
> Weitere Informationen zum Ausführen von SEFAUtil finden Sie im Blog Artikel "so wird es[gemacht: SEFAUtil läuft?](https://go.microsoft.com/fwlink/?LinkId=278940)". 
  
### <a name="to-deploy-sefautil"></a>So stellen Sie das SEFAUtil-Tool bereit

1. Melden Sie sich bei dem Computer an, auf dem die Skype for Business Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder mit den erforderlichen Benutzerrechten installiert ist, wie unter **Delegieren von Setup Berechtigungen**beschrieben.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
3. Das SEFAUtil-Tool kann nur auf einem Computer ausgeführt werden, der zu einem vertrauenswürdigen Anwendungspool gehört. Falls erforderlich, definieren Sie einen vertrauenswürdigen Anwendungspool für den Front-End-Pool, in dem Sie SEFAUtil ausführen möchten. Führen Sie an der Eingabeaufforderung folgenden Befehl aus:
    
   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > Pool-FQDN: der FQDN des Servers oder Pools, der die SEFAUtil-Anwendung hosten soll (in der Regel ein Skype for Business-Front-End-Server oder-Pool).
    > Pool Registrar FQDN: der FQDN des Skype for Business-Front-End-Servers oder-Pools, der diesem Anwendungspool zugeordnet ist.
    > Pool Website: die Website-ID der Website, auf der dieser Pool verwaltet wird.

4. Definieren Sie das SEFAUtil-Tool als eine vertrauenswürdige Anwendung. Führen Sie an der Eingabeaufforderung folgenden Befehl aus:
    
   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > Sie können ggf. einen anderen Port verwenden. 
  
5. Aktivieren Sie die Topologie mit Ihren Änderungen. Führen Sie an der Eingabeaufforderung folgenden Befehl aus:
    
   ```powershell
   Enable-CsTopology
   ```

6. Wenn Sie dies noch nicht getan haben, laden Sie die Skype for Business Server-Version des SEFAUtil-Tools von [diesem Speicherort](https://www.microsoft.com/en-us/download/details.aspx?id=52631)herunter, und installieren Sie Sie in dem vertrauenswürdigen Anwendungspool, den Sie in Schritt 3 erstellt haben.
    
7. Gehen Sie wie folgt vor, um sicherzustellen, dass Ihr SEFAUtil-Tool korrekt ausgeführt wird: 
    
    a. Führen Sie das Tool an der Windows-Eingabeaufforderung mit Administratorberechtigungen aus, um die Anrufweiterleistungseinstellungen eines Benutzers in Ihrer Bereitstellung anzuzeigen.
    
    b. Zeigen Sie die Anrufweiterleitungseinstellungen eines Benutzers an. Führen Sie an der Eingabeaufforderung folgenden Befehl aus:
    
   ```console
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

Die Anrufweiterleitungseinstellungen für den Benutzer werden angezeigt.
    

