---
title: Installieren des WMI-abwärts Kompatibilitätspakets
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Install WMI Backward Compatibility package
ms:assetid: 38797fbd-06a0-4008-b099-158e7b5d7703
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204816(v=OCS.15)
ms:contentKeyID: 48183893
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c59e3ea03b3b6f4085f8acf461b1da3f32e21fa9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199398"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-wmi-backward-compatibility-package"></a>Installieren des WMI-abwärts Kompatibilitätspakets

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-02_

Wenn Sie versuchen, den Zusammenführungs-Assistenten des Topologie-Generators auszuführen, ohne das WMI-Abwärtskompatibilitätspaket zu installieren, tritt der folgende Fehler auf:

![WMI-Fehlermeldung](images/JJ204816.a007d2f2-fc85-430c-91eb-382b032469af(OCS.15).jpg "WMI-Fehlermeldung")

Wenn Sie versuchen, das **Merge-CsLegacytopology**-Cmdlet ohne Installieren des WMI-Abwärtskompatibilitätspakets auszuführen, erhalten Sie den folgenden Fehler:

![Fehler bei Windows PowerShell WMI-Anbieter](images/JJ204816.c510824e-1807-4c7e-bb28-c6cfea2eac1d(OCS.15).jpg "Fehler bei Windows PowerShell WMI-Anbieter")

So installieren Sie das WMI-Abwärtskompatibilitätspaket

1.  Navigieren Sie auf den Installationsmedien zu \\Setup\\amd64\\Setup\\OCSWMIBC. MSI.

2.  Installieren Sie OCSWMIBC.MSI.
    
    <div>
    

    > [!IMPORTANT]  
    > OCSWMIBC.msi muss auf dem Computer installiert werden, auf dem der Zusammenführungs-Assistent des Topologie-Generators ausgeführt wird. Es wird jedoch empfohlen, OCSWMIBC.msi auf allen Front-End-Servern in der Topologie auszuführen.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > OCSWMIBC. msi kann auf jedem Computer in der Domäne installiert werden, auf dem die lync Server 2013 Kernkomponenten und die lync Server 2013 Verwaltungsshell installiert sind, und über Zugriff auf die Office Communications Server 2007 R2 Topologie (WMI-Anbieter für Active Directory Domäne) verfügt. Dienste (AD DS) und SQL Server).

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

