---
title: 'Lync Server 2013: Erstellen von Registrierungsstellen-Konfigurationseinstellungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Registrar configuration settings
ms:assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182601(v=OCS.15)
ms:contentKeyID: 48185758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81aec9ee6923dc125769ad16a26390b23155852c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763469"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-registrar-configuration-settings-in-lync-server-2013"></a>Erstellen von Registrierungs Konfigurationseinstellungen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-03-17_

Mithilfe der Registrierungsstelle können Sie Proxyserver-Authentifizierungsmethoden konfigurieren. Das angegebene Authentifizierungsprotokoll legt fest, welche Art von Authentifizierungsaufforderungen die Server im Pool an die Clients senden. Die folgenden Protokolle sind verfügbar:

  - **Kerberos**   Dies ist das am stärksten für Clients verfügbare kennwortbasierte Authentifizierungsschema, das jedoch normalerweise nur für Unternehmensclients verfügbar ist, da es eine Clientverbindung mit einem Schlüssel Verteilungs Center (Kerberos-Domänencontroller) erfordert. Diese Einstellung ist geeignet, wenn der Server nur Enterprise-Clients authentifiziert.

  - **NTLM**   hierbei handelt es sich um die kennwortbasierte Authentifizierung, die für Clients verfügbar ist, die ein Hash Schema für Abfrage Antworten auf das Kennwort verwenden. Für Clients ohne Verbindung mit einem Schlüsselverteilungscenter (Kerberos-Domänencontroller), beispielsweise für Remotebenutzer, steht nur diese Form der Authentifizierung zur Verfügung. Wenn ein Server ausschließlich Remotebenutzer authentifiziert, sollten Sie NTLM auswählen.

  - **Zertifikatauthentifizierung**   Dies ist die neue Authentifizierungsmethode, wenn der Serverzertifikate von lync Phone Edition-Clients, öffentlichen Telefonen, lync 2013 und der lync Windows Store-App abrufen muss. Wenn sich ein Benutzer bei lync Phone Edition-Clients anmeldet und erfolgreich durch die Bereitstellung einer Personal Identification Number (PIN) authentifiziert wird, stellt lync Server 2013 den SIP-URI dem Telefon zur Verfügung und stellt ein signiertes lync Server-Zertifikat oder ein Benutzerzertifikat bereit, das Joe (ex: SN=Joe@Contoso.com) auf dem Smartphone kennzeichnet. Dieses Zertifikat wird für die Authentifizierung beim Registrierungsdienst und den Webdiensten verwendet.

<div>


> [!NOTE]  
> Es wird empfohlen, sowohl Kerberos als auch NTLM zu aktivieren, wenn ein Server die Authentifizierung von Remote- und Unternehmensclients unterstützt. Durch eine Kommunikation des Edgeservers mit den internen Servern wird gewährleistet, dass Remoteclients nur die NTLM-Authentifizierung verwenden können. Wenn auf diesen Servern nur Kerberos verwendet wird, ist eine Authentifizierung von Remotebenutzern nicht möglich. Wenn Unternehmensbenutzer sich ebenfalls über den Server authentifizieren, wird Kerberos verwendet.<BR>Wenn Sie lync Windows Store-App-Clients verwenden, müssen Sie die Zertifikatauthentifizierung aktivieren.



</div>

Führen Sie die folgenden Schritte aus, um eine neue Registrierungsstelle zu erstellen.

<div>

## <a name="to-create-new-registrar-configuration-settings"></a>So erstellen Sie neue Konfigurationseinstellungen für eine Registrierungsstelle

1.  Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder über entsprechende Benutzerrechte verfügt) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, bei jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie lync Server 2013 bereitgestellt haben.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **Registrierungsstelle**.

4.  Klicken Sie auf der Seite **Registrierungsstelle** auf **Neu**.

5.  Klicken Sie unter **Dienst auswählen** auf den Dienst, auf den die Registrierungsstelle angewendet werden soll, und klicken Sie anschließend auf **OK**.

6.  Wählen Sie im Abschnitt **Neue Registrierungsstelleneinstellung** je nach Funktionen der Clients und der Unterstützung in Ihrer Umgebung eine oder mehrere der folgenden Optionen aus:
    
      - **Kerberos-Authentifizierung aktivieren**: Die Server im Pool stellen Authentifizierungsaufforderungen mithilfe der Kerberos-Authentifizierung aus.
    
      - **NTLM-Authentifizierung aktivieren**: Die Server im Pool stellen Authentifizierungsaufforderungen mithilfe von NTLM aus.
    
      - **Zertifikatauthentifizierung aktivieren**: Die Server im Pool stellen Zertifikate an Clients aus.

7.  Klicken Sie auf **Commit ausführen**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

