---
title: Migrieren von Zugriffsnummern für die Einwahl
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate dial-in access numbers
ms:assetid: 568a94b7-a697-4ab2-9008-dc9ecc1c87c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204898(v=OCS.15)
ms:contentKeyID: 48184171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15ee86d78b75fe1928cb92459f8689aea2f6b1b8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029116"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a>Migrieren von Zugriffsnummern für die Einwahl

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-26_

Das Migrieren von Einwahlnummern erfordert zwei Schritte: Ausführen des Cmdlets " **Import-CsLegacyConfiguration** " (zuvor abgeschlossen in " [Import Policies and Settings](import-policies-and-settings.md)"), um Wählpläne und andere Einstellungen für die Einwahl Zugriffsnummer zu migrieren und das Cmdlet " **verschieben-CsApplicationEndpoint** " zum Migrieren der Kontaktobjekte auszuführen.

<div>

## <a name="to-migrate-dial-in-access-numbers"></a>So migrieren Sie Zugriffsnummern für die Einwahl

1.  Öffnen Sie das Office Communications Server 2007 R2 Verwaltungstool.

2.  Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf den Gesamtstrukturknoten, klicken Sie auf **Eigenschaften**, und klicken Sie dann auf **Eigenschaften der Konferenzzentrale**.

3.  Klicken Sie auf der Registerkarte **Zugriffstelefonnummern** auf **Verarbeitet vom Pool**, um die Zugriffstelefonnummern nach dem zugeordneten Pool zu ordnen und alle Zugriffnummern für den zu migrierenden Pool zu identifizieren.

4.  Zum Identifizieren der SIP-URI für jede Zugriffsnummer doppelklicken Sie auf die Zugriffsnummer, um das Dialogfeld **Nummer für die Konferenzzentrale bearbeiten** zu öffnen, und sehen Sie dann unter **SIP-URI** nach.

5.  Öffnen Sie die Lync Server-Verwaltungsshell.

6.  Führen Sie die folgenden Schritte aus, um jede Zugriffsnummer für die Einwahl in einen auf lync Server 2013 gehosteten Pool zu übertragen:
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

7.  Überprüfen Sie im Verwaltungstool Office Communications Server 2007 R2 auf der Registerkarte **Zugriffs** Telefonnummern, ob keine Einwahlnummern für den Office Communications Server 2007 R2 Pool verbleiben, von dem Sie migrieren.

</div>

</div>

<span> </span>

</div>

</div>

</div>

