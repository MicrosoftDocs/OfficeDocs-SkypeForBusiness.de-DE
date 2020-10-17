---
title: 'Lync Server 2013: Suchen nach lync Server Benutzern'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Search for Lync Server users
ms:assetid: 3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429701(v=OCS.15)
ms:contentKeyID: 48183871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b690b0880e1da838b3b8f15392e64c4f4c650c10
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510492"
---
# <a name="search-for-lync-server-users-in-lync-server-2013"></a>Suchen nach lync Server Benutzern in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-05-14_

Sie können die Ergebnisse einer Suchabfrage verwenden, um Benutzer für lync Server 2013 zu konfigurieren. Sie können anhand des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontonamens (Security Accounts Manager), der SIP-Adresse oder des Anschluss-URI (Uniform Resource Identifier) nach Benutzern suchen.

Ferner können Sie Benutzer über die Lync Server-Systemsteuerung oder das Snap-In Active Directory-Benutzer und -Computer suchen. Im folgenden Verfahren wird beschrieben, wie lync Server-Systemsteuerung für die Suche nach Benutzern verwendet wird.

<div>


> [!NOTE]  
> In einer Umgebung mit einer zentralen Gesamtstrukturtopologie sind die Suchergebnisse möglicherweise ungenau, wenn Sie anhand der E-Mail-Adresse nach einem Benutzer suchen. Stattdessen können Sie Benutzer durch Angabe eines SIP-Adressenpräfixes suchen, z. B. "sip:name", einen Suchfilter hinzufügen und eine SIP-Adresse auswählen, die einen Teil einer E-Mail-Adresse enthält, oder das Cmdlet <STRONG>Get-CSUser</STRONG> verwenden.



</div>

<div>

## <a name="to-search-for-one-or-more-users"></a>So suchen Sie nach einem oder mehreren Benutzern

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4.  Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen, die SIP-Adresse oder den Anschluss-URI des zu suchenden Benutzerkontos ein, und klicken Sie dann auf **Suchen**.

5.  (Optional) Geben Sie zusätzliche Suchkriterien ein, um die Ergebnisse zu beschränken:
    
    1.  Klicken Sie in der oberen rechten Ecke des Bildschirms oberhalb von **Suchergebnisse** auf die Pfeiltaste zum Erweitern des Fensters, und klicken Sie dann auf **Filter hinzufügen**.
    
    2.  Geben Sie die Benutzereigenschaft ein, indem Sie sie eingeben oder auf den Pfeil in der Dropdownliste klicken, um eine Benutzereigenschaft auszuwählen.
    
    3.  Klicken Sie in der Dropdownliste **Gleich** auf **Gleich** oder **Ungleich**.
    
    4.  Geben Sie im Textfeld die Suchkriterien ein, die Sie zum Filtern der Suchergebnisse verwenden möchten, und klicken Sie dann auf **Suchen**.

6.  Die Suchergebnisse werden unter **Suchergebnisse** angezeigt. Sie können bestimmte oder alle Benutzer in der Liste auswählen und für die ausgewählten Benutzer Konfigurationsaufgaben durchführen.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Anzeigen von Informationen zu Benutzerkonten, die für lync Server 2013 aktiviert sind](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)  
[Aktivieren und Deaktivieren von Benutzern für lync Server 2013](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

