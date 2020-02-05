---
title: 'Lync Server 2013: Suchen nach lync Server-Benutzern'
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
ms.openlocfilehash: 7134afbc86134471e8d536b36fc8e28142a64db2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764923"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="search-for-lync-server-users-in-lync-server-2013"></a>Suchen nach lync Server-Benutzern in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-05-14_

Sie können die Ergebnisse einer Suchabfrage verwenden, um Benutzer für lync Server 2013 zu konfigurieren. Sie können anhand des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontonamens (Security Accounts Manager), der SIP-Adresse oder des Anschluss-URI (Uniform Resource Identifier) nach Benutzern suchen.

Sie können mithilfe der lync Server-Systemsteuerung oder des Snap-Ins Active Directory-Benutzer und-Computer nach Benutzern suchen. Im folgenden Verfahren wird beschrieben, wie Sie mithilfe der lync Server-Systemsteuerung nach Benutzern suchen können.

<div>


> [!NOTE]  
> In einer Umgebung mit einer zentralen Gesamtstrukturtopologie sind die Suchergebnisse möglicherweise nicht korrekt, wenn Sie nach einem Benutzer anhand der e-Mail-Adresse des Benutzers suchen. Stattdessen können Sie nach Benutzern suchen, indem Sie ein SIP-Adresspräfix angeben, beispielsweise SIP: Name, einen Suchfilter hinzufügen und eine SIP-Adresse auswählen, die eine teilweise e-Mail-Adresse enthält, oder das Cmdlet " <STRONG>Get-CSUser</STRONG> " verwenden.



</div>

<div>

## <a name="to-search-for-one-or-more-users"></a>So suchen Sie nach einem oder mehreren Benutzern

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4.  Geben Sie im Feld **Benutzer suchen** den gesamten oder den ersten Teil des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontonamens, der SIP-Adresse oder des Leitungs-URIs des Benutzerkontos ein, nach dem Sie suchen möchten, und klicken Sie dann auf **Suchen**.

5.  (Optional) Geben Sie zusätzliche Suchkriterien ein, um die Ergebnisse einzuschränken:
    
    1.  Klicken Sie in der oberen rechten Ecke des Bildschirms oberhalb der **Suchergebnisse**auf die Schaltfläche zum Erweitern des Pfeils, und klicken Sie dann auf **Filter hinzufügen**.
    
    2.  Geben Sie die Benutzereigenschaft ein, indem Sie Sie eingeben oder in der Dropdownliste auf den Pfeil klicken, um eine Benutzereigenschaft auszuwählen.
    
    3.  Klicken Sie in der Liste **gleich** an auf **gleich** oder **ungleich**.
    
    4.  Geben Sie im Textfeld die Suchkriterien ein, die Sie zum Filtern der Suchergebnisse verwenden möchten, und klicken Sie dann auf **Suchen**.

6.  Die Suchergebnisse werden unter **Suchergebnisse**angezeigt. Sie können einen oder alle Benutzer in der Liste auswählen und Konfigurationsaufgaben für die von Ihnen ausgewählten Benutzer durchführen.

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

