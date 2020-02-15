---
title: 'Lync Server 2013: Aktivieren oder Deaktivieren von Verbund-und öffentlichen Chat Verbindungen'
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
ms.openlocfilehash: 9281b4dab225ddb336dbc74a5d2892f0f4a015d5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040203"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-federation-and-public-im-connectivity-in-lync-server-2013"></a>Aktivieren oder Deaktivieren der Verbund-und Public Chat-Konnektivität in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-06-24_

Die Unterstützung für einen Partnerverbund ist erforderlich, um Benutzern mit einem Konto in einer vertrauenswürdigen Kunden- oder Partnerorganisation – Partnerdomänen und Benutzer eines unterstützten öffentlichen Sofortnachrichtenanbieters eingeschlossen – die Zusammenarbeit mit Benutzern in Ihrer Organisation zu ermöglichen. Der Partnerverbund ist auch erforderlich, um einen gehosteten Exchange-Dienstanbieter zu verwenden, um Voicemail für Enterprise-VoIP-Benutzer bereitzustellen, deren Postfächer sich in einem gehosteten Exchange-Dienst befinden, z. B. Microsoft Exchange Online. Wenn Sie eine Vertrauensstellung mit diesen externen Domänen hergestellt haben, können Sie Benutzer in diesen Domänen autorisieren, um auf Ihre Bereitstellung zuzugreifen und an lync Server Kommunikation teilzunehmen. Diese Vertrauensstellung wird Partnerverbund genannt, und es besteht weder ein Zusammenhang mit noch eine Abhängigkeit von einer Active Directory-Vertrauensstellung.

Zur Unterstützung des Benutzerzugriffs auf Partnerdomänen müssen Sie den Partnerverbund aktivieren. Wenn Sie den Partnerverbund für Ihre Organisation aktivieren, müssen Sie auch angeben, ob die folgenden Optionen implementiert werden sollen:

  - **Partnerdomänen Erkennung**   aktivieren Wenn Sie diese Option aktivieren, verwendet lync Server Domain Name System (DNS) Datensätze, um zu versuchen, Domänen zu ermitteln, die nicht in der Liste der zugelassenen Domänen aufgeführt sind, und den eingehenden Datenverkehr von ermittelten Partner Partnern automatisch auswerten und den Datenverkehr basierend auf der Vertrauensebene, dem Umfang des Datenverkehrs und den Administratoreinstellungen einschränken oder blockieren Wenn Sie diese Option nicht auswählen, wird der Verbundbenutzer Zugriff nur für Benutzer in den Domänen aktiviert, die Sie in die Liste zugelassene Domänen einschließen. Unabhängig davon, ob Sie diese Option auswählen, können Sie angeben, dass einzelne Domänen blockiert oder zugelassen werden sollen, einschließlich der Einschränkung des Zugriffs auf bestimmte Server, auf denen die Zugriffs-Edgedienst in der Verbunddomäne aufgeführt wird. Ausführliche Informationen zum Steuern des Zugriffs durch Verbunddomänen finden Sie unter [Konfigurieren der Unterstützung für zugelassene externe Domänen in lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).

  - **Senden eines Haftungsausschlusses an Verbundpartner**     Haftungsausschluss Hinweis wird an Verbundpartner gesendet, dass die Archivierung in Ihrer Bereitstellung erfolgt. Wenn Sie die Archivierung der externen Kommunikation mit Verbundpartnerdomänen unterstützen, sollten Sie die Benachrichtigung über den Archivierungshaftungsausschluss aktivieren, um die Partner über die Archivierung ihrer Nachrichten in Kenntnis zu setzen.

Wenn Sie den Zugriff durch Benutzer von Partnerdomänen zu einem späteren Zeitpunkt temporär oder dauerhaft unterbinden möchten, können Sie den Partnerverbund für Ihre Organisation deaktivieren. Verwenden Sie das Verfahren in diesem Abschnitt, um den Partnerbenutzerzugriff für Ihre Organisation zu aktivieren oder zu deaktivieren und um die geeigneten Partnerverbundoptionen festzulegen, die für Ihre Organisation unterstützt werden sollen.

<div>


> [!NOTE]  
> Das Aktivieren des partnerverbunds für Ihre Organisation gibt nur an, dass Ihre Server mit dem Zugriffs-Edgedienst Routing an Verbunddomänen unterstützen. Benutzer in Verbunddomänen können erst an Chatnachrichten oder Konferenzen in Ihrer Organisation teilnehmen, wenn Sie mindestens eine Richtlinie zur Unterstützung des Zugriffs durch Verbundbenutzer konfiguriert haben. Benutzer von öffentlichen Instant Messaging-Dienstanbietern können erst dann an Chatnachrichten oder Konferenzen in Ihrer Organisation teilnehmen, wenn Sie mindestens eine Richtlinie für die Unterstützung von Verbindungen mit öffentlichen Chat Diensten konfiguriert haben. Lync Server können einen gehosteten Exchange-Dienst nicht verwenden, um Mailboxansage, Outlook Voice Access (einschließlich Voicemail) oder automatische Telefonzentralendienste für Benutzer bereitzustellen, deren Postfächer sich in einem gehosteten Exchange-Dienst befinden, bis Sie eine Richtlinie für gehostete Voicemail konfigurieren , die Routinginformationen bereitstellt. Ausführliche Informationen zum Konfigurieren von Richtlinien für die Kommunikation mit Benutzern von Verbunddomänen in anderen Organisationen finden Sie unter <A href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Verwalten von SIP-Verbunddomänen für Ihre Organisation in lync Server 2013</A> in der Betriebsdokumentation. Wenn Sie außerdem die Kommunikation mit Benutzern von Chat Dienstanbietern unterstützen möchten, müssen Sie Richtlinien zur Unterstützung dieser Dienste konfigurieren und auch die Unterstützung für die einzelnen Dienstanbieter konfigurieren, die Sie unterstützen möchten. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-manage-sip-federated-providers-for-your-organization.md">Verwalten von SIP-Verbund Anbietern für Ihre Organisation in lync Server 2013</A> in der Betriebsdokumentation. Ausführliche Informationen zum Erstellen einer Richtlinie für gehostete Voicemail finden Sie unter <A href="lync-server-2013-manage-hosted-voice-mail-policies.md">Manage Hosted Voice Mail Policies in lync Server 2013</A> in der Bereitstellungsdokumentation.



</div>

<div>

## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a>So aktivieren oder deaktivieren Sie den Partnerbenutzerzugriff für Ihre Organisation

1.  Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer** und dann auf **Konfiguration für Zugriffsedge**.

4.  Klicken Sie auf der Seite **Konfiguration für Zugriffsedge** auf **Global**, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.

5.  Führen Sie im Abschnitt **Konfiguration für Zugriffsedge bearbeiten** eine der folgenden Aktionen aus:
    
      - Aktivieren Sie das Kontrollkästchen **Zugriff durch Remotebenutzer aktivieren**, um den Zugriff durch Remotebenutzer für Ihre Organisation zuzulassen.
    
      - Deaktivieren Sie das Kontrollkästchen **Kommunikation mit Partnerbenutzern aktivieren**, um den Partnerbenutzerzugriff für Ihre Organisation zu deaktivieren.

6.  Führen Sie nach Aktivierung des Kontrollkästchens **Kommunikation mit Partnerbenutzern aktivieren** eine der folgenden Aktionen aus:
    
    1.  Aktivieren Sie das Kontrollkästchen **Suche von Partnerdomänen aktivieren**, um die automatische Suche von Partnerdomänen zu unterstützen.
    
    2.  Wenn Ihre Organisation die Archivierung der externen Kommunikation unterstützt, aktivieren Sie das Kontrollkästchen **Archivierungshaftungsausschluss an Verbundpartner senden**.

7.  Klicken Sie auf **Commit**.

Damit Verbundbenutzer mit Benutzern in ihrer lync Server 2013-Bereitstellung zusammenarbeiten können, müssen Sie auch mindestens eine Richtlinie für den externen Zugriff konfigurieren, um den Verbundbenutzer Zugriff zu unterstützen. Ausführliche Informationen finden Sie unter [configure Policies to Control Federated User Access in lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md) in der Bereitstellungsdokumentation oder in der Betriebsdokumentation. Informationen zum Steuern des Zugriffs auf bestimmte Verbunddomänen finden Sie unter [Konfigurieren der Unterstützung für zugelassene externe Domänen in lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.

</div>

<div>

## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a>Aktivieren oder Deaktivieren von Verbund-und öffentlichen Instant Messaging-Verbindungen mithilfe von Windows PowerShell-Cmdlets

Verbund-und öffentliche Instant Messaging-Verbindungen können auch mit Windows PowerShell und dem Cmdlet "csaccessedgeconfiguration nicht angeben" verwaltet werden. Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.

<div>

## <a name="to-enable-federation-and-public-im-connectivity"></a>So aktivieren Sie Partnerverbund und Verbindungen mit öffentlichen Chat Diensten

  - Legen Sie den Wert der Eigenschaft **AllowFederatedUsers** auf "True" ($True) fest, um den Partnerverbund und die Verbindung mit öffentlichen Sofortnachrichtendiensten zu aktivieren:
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-disable-federation-and-public-im-connectivity"></a>So deaktivieren Sie Verbund-und öffentliche Instant Messaging-Verbindungen

  - Legen Sie den Wert der Eigenschaft **AllowFederatedUsers** auf "False" ($False) fest, um den Partnerverbund und die Verbindung mit öffentlichen Sofortnachrichtendiensten zu deaktivieren:
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

