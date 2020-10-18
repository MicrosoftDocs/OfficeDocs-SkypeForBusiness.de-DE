---
title: 'Lync Server 2013: Einrichten der Kerberos-Authentifizierung'
description: 'Lync Server 2013: Einrichten der Kerberos-Authentifizierung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Kerberos authentication
ms:assetid: dd8009ef-6265-4cc0-b2c7-e474cd1f4b09
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398976(v=OCS.15)
ms:contentKeyID: 48185601
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb461968bc073edbfe640f609257f3e84c192461
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577231"
---
# <a name="setting-up-kerberos-authentication-in-lync-server-2013"></a>Einrichten der Kerberos-Authentifizierung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-21_

Lync Server 2013 unterstützt NTLM-und Kerberos-Authentifizierung für Webdienste. Office Communications Server 2007 und Office Communications Server 2007 R2 verwendet die standardmäßigen RTCComponentService und RTCService als Benutzerkonten zum Ausführen der Webdienste Anwendungspools, sodass ein Dienstprinzipalname (Service Principal Name, SPN) den Benutzerkonten zugewiesen und als Authentifizierungs Prinzipal fungieren kann. Lync Server verwendet Network Service zum Ausführen von Webdienste, und Network Service kann keine SPNs zugewiesen werden.

Um das Problem zu beheben, dass keine Active Directory-Objekte zum Speichern der SPNs zur Verfügung stehen, können lync Server-Systemsteuerung Computerkonto-Objekte zu diesem Zweck verwenden. Die Computerkontoobjekte können die Dienstprinzipalnamen enthalten und unterliegen keinem Kennwortablauf, was bei der Verwendung von Benutzerkonten in früheren Versionen ein Problem darstellte.

Verwenden Sie Windows PowerShell-Cmdlets, um die Computerobjekte für die Bereitstellung der Kerberos-Authentifizierung zu konfigurieren.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Voraussetzungen für die Aktivierung der Kerberos-Authentifizierung in lync Server 2013](lync-server-2013-prerequisites-for-enabling-kerberos-authentication.md)

  - [Erstellen eines Kerberos-Authentifizierungs Kontos in lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md)

  - [Zuweisen eines Kerberos-Authentifizierungs Kontos zu einem Standort in lync Server 2013](lync-server-2013-assign-a-kerberos-authentication-account-to-a-site.md)

  - [Einrichten von Kennwörtern für das Kerberos-Authentifizierungs Konto in lync Server 2013](lync-server-2013-setting-up-kerberos-authentication-account-passwords.md)

  - [In lync Server 2013 hinzufügen der Kerberos-Authentifizierung zu anderen Websites](lync-server-2013-add-kerberos-authentication-to-other-sites.md)

  - [In lync Server 2013 Entfernen der Kerberos-Authentifizierung von einer Website](lync-server-2013-remove-kerberos-authentication-from-a-site.md)

  - [Testen und melden des Status und der Zuweisung der Kerberos-Authentifizierung in lync Server 2013](lync-server-2013-testing-and-reporting-the-status-and-assignment-of-kerberos-authentication.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

