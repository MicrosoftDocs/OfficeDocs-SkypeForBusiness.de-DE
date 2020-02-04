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
ms.openlocfilehash: 0c3b8d474ff451a488124ebfbae0ff0872a6cca1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730555"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-wmi-backward-compatibility-package"></a>Installieren des WMI-abwärts Kompatibilitätspakets

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-02_

Wenn Sie versuchen, den Zusammenführungs-Assistenten des Topologie-Generators auszuführen, ohne das WMI-abwärts Kompatibilitätspaket zu installieren, wird der folgende Fehler angezeigt:

![WMI-Fehlermeldung](images/JJ204816.a007d2f2-fc85-430c-91eb-382b032469af(OCS.15).jpg "WMI-Fehlermeldung")

Wenn Sie versuchen, das **Merge-CsLegacytopology-** Cmdlet auszuführen, ohne das WMI-abwärts Kompatibilitätspaket zu installieren, wird der folgende Fehler angezeigt:

![Windows PowerShell-WMI-Anbieterfehler](images/JJ204816.c510824e-1807-4c7e-bb28-c6cfea2eac1d(OCS.15).jpg "Windows PowerShell-WMI-Anbieterfehler")

So installieren Sie das WMI-abwärts Kompatibilitätspaket

1.  Navigieren Sie auf Ihrem Installationsmedium zu \\Setup\\amd64\\Setup\\OCSWMIBC. MSI.

2.  Installieren Sie OCSWMIBC. MSI.
    
    <div>
    

    > [!IMPORTANT]  
    > OCSWMIBC. msi muss auf dem Computer installiert sein, auf dem der Zusammenführungs-Assistent des Topologie-Generators ausgeführt wird. Es wird jedoch empfohlen, OCSWMIBC. msi auf allen Front-End-Servern in Ihrer Topologie zu installieren.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > OCSWMIBC. msi kann auf jedem Computer in der Domäne installiert werden, auf dem die lync Server 2013-Core-Komponenten und die lync Server 2013-Verwaltungsshell installiert sind, und Zugriff auf die Office Communications Server 2007 R2-Topologie (WMI-Anbieter zu Active Directory-Domäne Dienste (AD DS) und SQL Server).

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

