---
title: 'Lync Server 2013: Konfigurieren der Unternehmenszertifizierungsstelle für die Smartcard-Authentifizierung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Enterprise CA for smart card authentication
ms:assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308571(v=OCS.15)
ms:contentKeyID: 54973692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: abfbbb7a7f7787ab5490db1542c4435368a84ca0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532562"
---
# <a name="configuring-enterprise-ca-for-smart-card-authentication-in-lync-server-2013"></a>Konfigurieren der Unternehmenszertifizierungsstelle für die Smartcard-Authentifizierung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-07-03_

Im folgenden Abschnitt wird beschrieben, wie Sie eine Unternehmensstammzertifizierungsstelle (Certification Authority, ca) zur Unterstützung der Smartcard-Authentifizierung konfigurieren. Informationen zum Installieren einer Stammzertifizierungsstelle für Unternehmen finden Sie unter Installieren einer Stammzertifizierungsstelle für Unternehmen unter [https://go.microsoft.com/fwlink/p/?LinkID=313364](https://go.microsoft.com/fwlink/p/?linkid=313364) .

<div>

## <a name="configuring-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a>Konfigurieren einer Stammzertifizierungsstelle für Unternehmen zur Unterstützung der Smartcard-Authentifizierung

In den folgenden Schritten wird das Konfigurieren einer Stammzertifizierungsstelle für Unternehmen zur Unterstützung der Smartcard-Authentifizierung beschrieben:

1.  Melden Sie sich mit einem Domänenadministratorkonto beim Enterprise-Zertifizierungsstellencomputer an.

2.  Starten Sie System-Manager, und stellen Sie sicher, dass die Webregistrierungs Rolle der Zertifizierungsstelle installiert ist.

3.  Öffnen Sie im Menü **Verwaltungs Tools** die Verwaltungskonsole der **Zertifizierungsstelle** .

4.  Erweitern Sie im Navigationsbereich die Option **Zertifizierungsstelle**.

5.  Klicken Sie mit der rechten Maustaste auf **Zertifikatvorlagen**, wählen Sie **neu**, und wählen Sie dann **Auszustellende Zertifikatvorlage**aus.

6.  Wählen Sie **Registrierungs-Agent**, Smartcard- **Benutzer**und Smartcard- **Anmeldung**aus.

7.  Klicken Sie auf **OK**.

8.  Klicken Sie mit der rechten Maustaste auf **Zertifikatvorlagen**.

9.  Wählen Sie **Manage**aus.

10. Öffnen Sie die Eigenschaften der Smartcard-Benutzervorlage.

11. Klicken Sie auf die Registerkarte **Sicherheit** .

12. Ändern Sie die Berechtigungen wie folgt:
    
      - Hinzufügen einzelner Benutzer Ad-Konten mit Berechtigungen zum Lesen/registrieren (zulassen) oder
    
      - Hinzufügen einer Sicherheitsgruppe, die Smartcard-Benutzer mit Berechtigungen zum Lesen/registrieren (zulassen) enthält, oder
    
      - Hinzufügen der Gruppe "Domänenbenutzer" mit Berechtigungen zum Lesen/registrieren (zulassen)

</div>

</div>

<span> </span>

</div>

</div>

</div>

