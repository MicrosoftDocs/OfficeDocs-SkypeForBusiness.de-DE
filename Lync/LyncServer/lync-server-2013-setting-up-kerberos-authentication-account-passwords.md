---
title: 'Lync Server 2013: Einrichten von Kennwörtern für das Kerberos-Authentifizierungs Konto'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Kerberos authentication account passwords
ms:assetid: b435f88e-4a77-4be7-b7e5-c17484303b74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412870(v=OCS.15)
ms:contentKeyID: 48185167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29e8887f35e6d60d7d3aa59a0aa05590df371618
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509672"
---
# <a name="setting-up-kerberos-authentication-account-passwords-in-lync-server-2013"></a>Einrichten von Kennwörtern für das Kerberos-Authentifizierungs Konto in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2010-11-03_

Nach dem Erstellen des Computerobjekts für das Kerberos-Authentifizierungskonto können Sie das Kennwort für das Konto einrichten. Sie führen das Windows PowerShell-Cmdlet aus, um das Kennwort des Kerberos-Kontos auf einem Server festzulegen. Sie können das Kennwort für das Objekt festlegen, das Sie für die Kerberos-Authentifizierung erstellt haben. Das Kennwort kann auf einen bekannten Wert festgelegt werden, ist aber standardmäßig ein beliebiges Kennwort. Das Kennwort steht allen Kerberos-Authentifizierungsquellen zur Verfügung, die dieses Konto verwenden. Verwenden Sie Windows PowerShell-Cmdlets zum Einrichten und Verwalten von Kerberos-Kontokennwörtern.

<div>


> [!NOTE]  
> Das Kerberos-Kontoobjekt ist ein Computerobjekt, verwendet jedoch den Useraccount-Parameter für Vorgänge in den Windows PowerShell-Cmdlets, auf die verwiesen wird. Beachten Sie, dass dies kein Fehler, sondern das beabsichtigte Verhalten des Cmdlets ist, wenn es für die Erstellung und Verwaltung von Kerberos-Konten verwendet wird.



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Festlegen eines Kennworts für das Kerberos-Authentifizierungs Konto auf einem Server in lync Server 2013](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)

  - [Synchronisieren eines Kennworts für das Kerberos-Authentifizierungs Konto mit IIS in lync Server 2013](lync-server-2013-synchronize-a-kerberos-authentication-account-password-to-iis.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

