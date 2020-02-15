---
title: 'Lync Server 2013: Übersicht über die lync Server-Hybridumgebung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Lync Server 2013 hybrid environment
ms:assetid: 0d16ec3a-28f0-4483-96e7-8e68f30398fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204669(v=OCS.15)
ms:contentKeyID: 48183399
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e32132faee3b52140d20a7f01e6a0bad0e88c620
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049607"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-lync-server-2013-hybrid-environment"></a>Übersicht über die lync Server 2013 Hybridumgebung

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-05-28_

Lync Server 2013 Hybridumgebung bezieht sich auf eine Bereitstellung, in der einige Benutzer mit der lokalen lync Server 2013 und anderen Benutzern in lync online verwaltet werden, aber Benutzer dieselbe Domäne wie user@contoso.com verwenden.

<div>

## <a name="about-this-guide"></a>Informationen zu diesem Leitfaden

In diesem Leitfaden werden die Aufgaben beschrieben, die erforderlich sind, um die lync Server 2013 Umgebung für die Interoperabilität mit lync online zu konfigurieren und dann Benutzer aus Ihrer lokalen Bereitstellung zur Verwendung von lync online zu migrieren.

</div>

<div>

## <a name="prerequisites"></a>Voraussetzungen

Sie müssen die folgenden Anwendungen und Dienstprogramme installiert haben, um die Aufgaben zum Konfigurieren einer Bereitstellung für Hybrid auszuführen. Die Installationsprogramme für diese Dateien sind auf den für Ihre Bereitstellung bereitgestellten Installationsmedien sowie auf den in der folgenden Liste aufgeführten Links enthalten.

  - [Active Directory-Verbunddienste (AD FS) 2.0](http://go.microsoft.com/fwlink/p/?linkid=257305)

  - [Microsoft-Verzeichnis Synchronisierungs Tool 9,1](http://go.microsoft.com/fwlink/p/?linkid=257307)

  - [Installieren von Windows PowerShell für einmaliges Anmelden mit AD FS](http://go.microsoft.com/fwlink/p/?linkid=398710)

  - Der Microsoft Online Services-Anmelde Assistent (msoidcli-7.0. msi) ist in der Desktop Einrichtung für Office 365 enthalten, die von der Seite mit den Downloads abgerufen werden kann, die über das Office 365-Verwaltungsportal verlinkt ist.

</div>

<div>

## <a name="administrator-credentials"></a>Administrator Anmeldeinformationen

Wenn Sie aufgefordert werden, Ihre Administratoranmeldeinformationen anzugeben, verwenden Sie den Benutzernamen und das Kennwort für das Administratorkonto für den Office 365 Mandanten. Diese Anmeldeinformationen werden auch beim Konfigurieren von Active Directory-Verbunddienste (AD FS) 2.0, Verzeichnissynchronisierung, einmaliges Anmelden, Verbund und Verschieben von Benutzern zu lync Online verwendet.

</div>

<div>

## <a name="connecting-to-lync-online-powershell"></a>Herstellen einer Verbindung mit lync Online PowerShell

Administratoren haben jetzt die Möglichkeit, lync Online und deren lync Online Benutzerkonten mit Windows PowerShell zu verwalten. Hierzu müssen Sie zuerst das lync Online-Connector-Modul aus dem Microsoft Download Center herunterladen und installieren (http://go.microsoft.com/fwlink/?LinkId=294688). Weitere Informationen zum herunterladen, installieren und Verwenden des lync Online-Connector-Moduls sowie ausführliche Informationen zur Verwendung von Windows PowerShell zum Verwalten von lync Online finden Sie unter [using Windows PowerShell to manage lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

</div>

</div>

<span> </span>

</div>

</div>

</div>

