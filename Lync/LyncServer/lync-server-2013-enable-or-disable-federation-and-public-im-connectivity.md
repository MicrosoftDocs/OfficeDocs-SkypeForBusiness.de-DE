---
title: 'Lync Server 2013: Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable federation and public IM connectivity
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edbf03ee2e2772e6df1425ffd666176c1947f0e4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736065"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-federation-and-public-im-connectivity-in-lync-server-2013"></a>Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-06-24_

Die Unterstützung für die Föderation ist erforderlich, damit Benutzer, die über ein Konto bei einem vertrauenswürdigen Kunden oder einer Partnerorganisation verfügen, einschließlich Partnerdomänen und Benutzer von öffentlichen Instant Messaging (im)-Anbieter Benutzern, die Sie unterstützen, die Zusammenarbeit mit Benutzern in Ihrem Organisation. Föderation muss auch einen gehosteten Exchange-Dienstanbieter verwenden, um Voicemail für Enterprise-VoIP-Benutzer bereitzustellen, deren Postfächer sich in einem gehosteten Exchange-Dienst wie Microsoft Exchange Online befinden. Wenn Sie eine Vertrauensstellung mit diesen externen Domänen eingerichtet haben, können Sie Benutzer in diesen Domänen autorisieren, auf Ihre Bereitstellung zuzugreifen und an der lync Server-Kommunikation teilzunehmen. Diese Vertrauensstellung wird als Föderation bezeichnet und ist nicht mit einer Active Directory-Vertrauensstellung verbunden oder abhängig davon.

Wenn Sie den Zugriff von Benutzern von Verbunddomänen unterstützen möchten, müssen Sie die Föderation aktivieren. Wenn Sie die Föderation für Ihre Organisation aktivieren, müssen Sie auch angeben, ob die folgenden Optionen implementiert werden sollen:

  - **Aktivieren der Partnerdomänen Erkennung**   Wenn Sie diese Option aktivieren, verwendet lync Server DNS-Einträge (Domain Name System), um zu versuchen, Domänen zu ermitteln, die nicht in der Liste der zulässigen Domänen aufgeführt sind, wobei der eingehende Datenverkehr von ermittelten Partner Partnern automatisch ausgewertet und der Datenverkehr basierend auf Vertrauenswürdigkeit, Datenverkehr und Administratoreinstellungen eingeschränkt oder blockiert wird. Wenn Sie diese Option nicht auswählen, wird der Verbundbenutzer Zugriff nur für Benutzer in den Domänen aktiviert, die Sie in die Liste zugelassene Domänen aufnehmen. Unabhängig davon, ob Sie diese Option auswählen, können Sie angeben, dass einzelne Domänen blockiert oder zulässig sein sollen, einschließlich der Beschränkung des Zugriffs auf bestimmte Server, auf denen der Access-Edgedienst in der Verbunddomäne ausgeführt wird. Details zum Steuern des Zugriffs durch Verbunddomänen finden Sie unter [Konfigurieren der Unterstützung für zulässige externe Domänen in lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).

  - **Senden einer Verzichtserklärung zur Archivierung an Föderationspartner**     Haftungsausschluss Hinweis wird an verbundene Partner gesendet, die die Archivierung in Ihrer Bereitstellung durchgeführt haben. Wenn Sie die Archivierung externer Kommunikation mit Verbundpartner Domänen unterstützen, sollten Sie die Benachrichtigung über Archivierungs Verzicht aktivieren, um die Partner zu warnen, dass Ihre Nachrichten archiviert werden.

Wenn Sie den Zugriff von Benutzern von Verbunddomänen später vorübergehend oder dauerhaft verhindern möchten, können Sie den Verbund für Ihre Organisation deaktivieren. Verwenden Sie das Verfahren in diesem Abschnitt, um den Zugriff auf den Verbundbenutzer für Ihre Organisation zu aktivieren oder zu deaktivieren, einschließlich der Angabe der entsprechenden Verbund Optionen, die für Ihre Organisation unterstützt werden sollen.

<div>


> [!NOTE]  
> Das Aktivieren des Föderations Unternehmens für Ihre Organisation gibt nur an, dass Ihre Server, auf denen der Access Edge-Dienst ausgeführt wird, Routing in Verbunddomänen unterstützen Benutzer in Verbunddomänen können erst dann an Chats oder Konferenzen in Ihrer Organisation teilnehmen, wenn Sie mindestens eine Richtlinie für die Unterstützung des Zugriffs von Verbundbenutzern konfiguriert haben. Benutzer von Anbietern öffentlicher Chat Dienste können erst dann an Chats oder Konferenzen in Ihrer Organisation teilnehmen, wenn Sie mindestens eine Richtlinie für die Unterstützung öffentlicher Chats konfiguriert haben. Lync Server kann einen gehosteten Exchange-Dienst nicht zum Bereitstellen von Anrufbeantwortung, Outlook Voice Access (einschließlich Voicemail) oder automatischen Telefonzentralen Diensten für Benutzer verwenden, deren Postfächer sich in einem gehosteten Exchange-Dienst befinden, bis Sie eine gehostete Voicemail-Richtlinie konfigurieren. , in dem Routinginformationen bereitgestellt werden. Details zum Konfigurieren von Richtlinien für die Kommunikation mit Benutzern von Verbunddomänen in anderen Organisationen finden Sie unter <A href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Verwalten von SIP-Verbunddomänen für Ihre Organisation in lync Server 2013</A> in der Betriebsdokumentation. Wenn Sie die Kommunikation mit Benutzern von Chat Dienstanbietern unterstützen möchten, müssen Sie außerdem Richtlinien für deren Unterstützung konfigurieren und auch die Unterstützung für die einzelnen Dienstanbieter konfigurieren, die Sie unterstützen möchten. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-manage-sip-federated-providers-for-your-organization.md">Verwalten von SIP-Verbund Anbietern für Ihre Organisation in lync Server 2013</A> in der Betriebsdokumentation. Details zum Erstellen einer gehosteten Voicemail-Richtlinie finden Sie unter <A href="lync-server-2013-manage-hosted-voice-mail-policies.md">Verwalten von gehosteten Voicemail-Richtlinien in lync Server 2013</A> in der Bereitstellungsdokumentation.



</div>

<div>

## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a>So aktivieren oder deaktivieren Sie den Verbundbenutzer Zugriff für Ihre Organisation

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **externer Benutzer Zugriff**, und klicken Sie dann auf **Access-Edge-Konfiguration**.

4.  Klicken Sie auf der Seite **Access Edge Configuration** auf **Global**, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.

5.  Führen Sie in " **Access-Edge-Konfiguration bearbeiten**" eine der folgenden Aktionen aus:
    
      - Aktivieren Sie das Kontrollkästchen **Kommunikation mit Verbundbenutzern aktivieren** , um den Zugriff durch den Verbundbenutzer für Ihre Organisation zu aktivieren.
    
      - Wenn Sie den Verbundbenutzer Zugriff für Ihre Organisation deaktivieren möchten, deaktivieren Sie das Kontrollkästchen **Kommunikation mit verbundenen Benutzern aktivieren** .

6.  Wenn Sie das Kontrollkästchen **Kommunikation mit Verbundbenutzern aktivieren** aktiviert haben, gehen Sie folgendermaßen vor:
    
    1.  Wenn Sie die automatische Ermittlung von Partnerdomänen unterstützen möchten, aktivieren Sie das Kontrollkästchen **Discovery-Partnerdomänen Erkennung aktivieren** .
    
    2.  Wenn Ihre Organisation die Archivierung externer Kommunikation unterstützt, aktivieren Sie das Kontrollkästchen **Archivierungs Ausschluss an verbundene Partner senden** .

7.  Klicken Sie auf **Commit ausführen**.

Damit Verbundbenutzer mit Benutzern in ihrer lync Server 2013-Bereitstellung zusammenarbeiten können, müssen Sie auch mindestens eine Richtlinie für den externen Zugriff konfigurieren, um den Zugriff durch den Verbundbenutzer zu unterstützen. Ausführliche Informationen finden Sie unter [Konfigurieren von Richtlinien zum Steuern des Zugriffs von Verbundbenutzern in lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md) in der Bereitstellungsdokumentation oder in der Betriebsdokumentation. Informationen zum Steuern des Zugriffs auf bestimmte Föderationsdomänen finden Sie unter [Konfigurieren der Unterstützung für zulässige externe Domänen in lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.

</div>

<div>

## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a>Aktivieren oder Deaktivieren von Verbund-und öffentlichen Chat Verbindungen mithilfe von Windows PowerShell-Cmdlets

Verbund-und öffentliche Chat Verbindungen können auch mithilfe von Windows PowerShell und dem Cmdlet "Satz-csaccessedgeconfiguration nicht angeben" verwaltet werden. Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.

<div>

## <a name="to-enable-federation-and-public-im-connectivity"></a>So aktivieren Sie Verbund-und öffentliche Chat Verbindungen

  - Um Verbund-und öffentliche Chat Verbindungen zu aktivieren, setzen Sie den Wert der **AllowFederatedUsers** -Eigenschaft auf true ($true):
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-disable-federation-and-public-im-connectivity"></a>So deaktivieren Sie die Verbindung zwischen Föderation und öffentlichen Chats

  - Zum Deaktivieren der Konnektivität für Verbund-und öffentliche Chats setzen Sie den Wert der **AllowFederatedUsers** -Eigenschaft auf false ($false):
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

