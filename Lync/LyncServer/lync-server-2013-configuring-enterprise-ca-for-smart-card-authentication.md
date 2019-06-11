---
title: 'Lync Server 2013: Konfigurieren der Unternehmenszertifizierungsstelle für die Smartcard-Authentifizierung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Enterprise CA for smart card authentication
ms:assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308571(v=OCS.15)
ms:contentKeyID: 54973692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 890a69d1c863702db0a70cfb2ce3d61f6a75eeae
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839258"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-ca-for-smart-card-authentication-in-lync-server-2013"></a>Konfigurieren der Unternehmenszertifizierungsstelle für die Smartcard-Authentifizierung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-07-03_

Im folgenden Abschnitt wird beschrieben, wie Sie eine Unternehmensstammzertifizierungsstelle konfigurieren, um die Smartcard-Authentifizierung zu unterstützen. Informationen zum Installieren einer Unternehmensstammzertifizierungsstelle finden Sie unter Installieren einer Unternehmensstammzertifizierungsstelle [http://go.microsoft.com/fwlink/p/?LinkID=313364](http://go.microsoft.com/fwlink/p/?linkid=313364)unter.

<div>

## <a name="configuring-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a>Konfigurieren einer Unternehmensstammzertifizierungsstelle zur Unterstützung der Smartcard-Authentifizierung

In den folgenden Schritten wird das Konfigurieren einer Stammzertifizierungsstelle im Unternehmen zur Unterstützung der SmartCard-Authentifizierung beschrieben:

1.  Melden Sie sich beim CA-Computer des Unternehmens mit dem Konto eines Domänenadministrators an.

2.  Starten Sie den System-Manager und überprüfen Sie, ob die Zertifizierungsstellen-Webregistrierungsrolle installiert ist.

3.  Öffnen Sie im Menü **Verwaltungstools** die Verwaltungskonsole **Zertifizierungsstelle**.

4.  Erweitern Sie im Navigationsbereich den Knoten **Zertifizierungsstelle**.

5.  Klicken Sie mit der rechten Maustaste auf **Zertifikatvorlagen**, wählen Sie **Neu** und anschließend **Auszustellende Zertifikatvorlage** aus.

6.  Wählen Sie **Enrollment Agent**, **SmartCard-Benutzer** und **SmartCard-Anmeldung** aus.

7.  Klicken Sie anschließend auf **OK**.

8.  Klicken Sie mit der rechten Maustaste auf **Zertifikatvorlagen**.

9.  Wählen Sie **Verwalten** aus.

10. Öffnen Sie die Eigenschaften der Vorlage „SmartCard-Benutzer“.

11. Klicken Sie auf die Registerkarte **Sicherheit**.

12. Ändern Sie die Berechtigungen wie folgt:
    
      - Fügen Sie einzelne AD-Konten mit den Berechtigungen „Lesen/Registrieren (Zulassen)“ hinzu, oder
    
      - Fügen Sie eine Sicherheitsgruppe hinzu, die SmartCard-Benutzer mit den Berechtigungen „Lesen/Registrieren (Zulassen)“ enthält, hinzu, oder
    
      - Fügen Sie die Gruppe „Domänenbenutzer“ mit den Berechtigungen „Lesen/Registrieren (Zulassen“) hinzu

</div>

</div>

<span> </span>

</div>

</div>

</div>

