---
title: 'Lync Server 2013: Übersicht über die lync Server-Hybridumgebung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of the Lync Server 2013 hybrid environment
ms:assetid: 0d16ec3a-28f0-4483-96e7-8e68f30398fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204669(v=OCS.15)
ms:contentKeyID: 48183399
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0420e4aaded9f5ae90d26c4cbdc176e7fb4c6bb5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825324"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-lync-server-2013-hybrid-environment"></a>Übersicht über die lync Server 2013-Hybridumgebung

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-05-28_

Die lync Server 2013-Hybridumgebung bezieht sich auf eine Bereitstellung, in der einige Benutzer mit dem lokalen lync Server 2013 und anderen Benutzern in lync Online vernetzt sind, Benutzer jedoch dieselbe Domäne wie user@contoso.com verwenden.

<div>

## <a name="about-this-guide"></a>Informationen zu diesem Leitfaden

In diesem Leitfaden werden die Aufgaben beschrieben, die erforderlich sind, um Ihre lync Server 2013-Umgebung für die Interoperabilität mit lync online zu konfigurieren und dann Benutzer aus Ihrer lokalen Bereitstellung in die Verwendung von lync online zu verschieben.

</div>

<div>

## <a name="prerequisites"></a>Voraussetzungen

Sie müssen die folgenden Anwendungen und Dienstprogramme installiert haben, um die Aufgaben für die Konfiguration einer Bereitstellung für Hybrid abzuschließen. Die Installationsprogramme für diese Dateien sind auf den für Ihre Bereitstellung bereitgestellten Installationsmedien sowie auf den Links in der folgenden Liste enthalten.

  - [Active Directory-Verbunddienste (AD FS) 2,0](http://go.microsoft.com/fwlink/p/?linkid=257305)

  - [Microsoft-Verzeichnis Synchronisierungs Tool 9,1](http://go.microsoft.com/fwlink/p/?linkid=257307)

  - [Installieren von Windows PowerShell für einmaliges Anmelden mit AD FS](http://go.microsoft.com/fwlink/p/?linkid=398710)

  - Der Microsoft Online Services-Anmelde Assistent (msoidcli-7.0. msi) ist im Desktop-Setup für Office 365 enthalten, das über die Download Seite mit dem Office 365-Administratorportal abgerufen werden kann.

</div>

<div>

## <a name="administrator-credentials"></a>Administrator Anmeldeinformationen

Wenn Sie aufgefordert werden, Ihre Administratoranmeldeinformationen anzugeben, verwenden Sie den Benutzernamen und das Kennwort für das Administratorkonto für Ihren Office 365-Mandanten. Sie verwenden diese Anmeldeinformationen auch, wenn Sie Active Directory-Verbunddienste (AD FS) 2,0, Verzeichnissynchronisierung, einmaliges Anmelden, Föderation und Verschieben von Benutzern nach lync Online konfigurieren.

</div>

<div>

## <a name="connecting-to-lync-online-powershell"></a>Herstellen einer Verbindung mit lync Online PowerShell

Administratoren haben jetzt die Möglichkeit, Windows PowerShell zum Verwalten von lync Online und ihren lync Online-Benutzerkonten zu verwenden. Dazu müssen Sie zuerst das lync Online Connector-Modul aus dem Microsoft Download Center herunterladen und installieren (http://go.microsoft.com/fwlink/?LinkId=294688). Weitere Informationen zum herunterladen, installieren und Verwenden des lync Online-Connector-Moduls sowie ausführliche Informationen zur Verwendung von Windows PowerShell zum Verwalten von lync Online finden Sie unter [Verwenden von Windows PowerShell zum Verwalten von lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

</div>

</div>

<span> </span>

</div>

</div>

</div>

