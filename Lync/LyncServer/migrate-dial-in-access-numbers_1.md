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
ms.openlocfilehash: a13fdf36dcd36dc71df8ffa06c273c2b2b0f0292
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762933"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a>Migrieren von Zugriffsnummern für die Einwahl

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-26_

Zum Migrieren von Einwahl Zugriffsnummern sind zwei Schritte erforderlich: Ausführen des Cmdlets " **Import-CsLegacyConfiguration** " (bereits in [Importieren von Richtlinien und Einstellungen](import-policies-and-settings.md)) zum Migrieren von Wählplänen und anderen Einstellungen für Einwahl Zugriffsnummern und Ausführen des Cmdlets **Move-CsApplicationEndpoint** , um die Kontaktobjekte zu migrieren.

<div>

## <a name="to-migrate-dial-in-access-numbers"></a>So migrieren Sie Einwahl Zugriffsnummern

1.  Öffnen Sie das Office Communications Server 2007 R2-Verwaltungstool.

2.  Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf den Knoten Gesamtstruktur, klicken Sie auf **Eigenschaften**, und klicken Sie dann auf **Eigenschaften der Konferenzzentrale**.

3.  Klicken Sie auf der Registerkarte **Access-Telefonnummern** auf **gewartet nach Pool** , um die Access-Telefonnummern nach dem zugehörigen Pool zu sortieren, und identifizieren Sie alle Zugriffsnummern für den Pool, aus dem Sie migrieren möchten.

4.  Um den SIP-URI für jede Zugriffsnummer zu identifizieren, doppelklicken Sie auf die Zugriffsnummer, um das Dialogfeld **Konferenzzentrale Nummer bearbeiten** zu öffnen, und schauen Sie unter **SIP-URI**nach.

5.  Öffnen Sie die lync Server-Verwaltungsshell.

6.  Führen Sie die folgenden Schritte aus, um jede Einwahl Zugriffsnummer in einen Pool zu verschieben, der auf lync Server 2013 gehostet wird:
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

7.  Überprüfen Sie im Office Communications Server 2007 R2-Verwaltungstool auf der Registerkarte **Access-Telefonnummern** , ob keine Einwahl Zugriffsnummern für den Office Communications Server 2007 R2-Pool vorhanden sind, von dem aus Sie migrieren.

</div>

</div>

<span> </span>

</div>

</div>

</div>

