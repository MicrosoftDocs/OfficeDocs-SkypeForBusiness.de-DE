---
title: 'Lync Server 2013: Richtlinien für gehostete Voicemail'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted voice mail policies
ms:assetid: d62a35ed-cbe2-4f06-86b4-e192c18435c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398932(v=OCS.15)
ms:contentKeyID: 48185506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01e844e62934a697b12afa76d2e9c9405a30a4a4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043177"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-voice-mail-policies-in-lync-server-2013"></a>Gehostete Voicemail-Richtlinien in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-01_

Eine *Richtlinie für gehostete Voicemail* stellt Informationen für die lync Server 2013 ExUM-Routing Anwendung bereit, in der die Anrufe für Benutzer weitergeleitet werden, deren Postfächer sich in einem gehosteten Exchange-Dienst befinden.

<div>


> [!NOTE]  
> Gehostete Voicemail-Richtlinien sind nur für die lync Server 2013 Integration in gehostete Exchange um erforderlich. Für die Integration in lokale Exchange UM-Dienste werden die Richtlinien nicht benötigt.



</div>

<div>

## <a name="hosted-voice-mail-policy-scope"></a>Bereich einer Richtlinie für gehostete Voicemail

Der Bereich einer Richtlinie für gehostete Voicemail bestimmt die Hierarchieebene, auf der die Richtlinie angewendet wird. Sie können Richtlinien für gehostete Voicemail mit folgenden Bereichsebenen konfigurieren:

  - Die *globale* Richtlinie kann sich potenziell auf alle Benutzer in der lync Server 2013-Bereitstellung auswirken. Wenn ein Benutzer für den Zugriff auf gehostete Exchange UM-Dienste aktiviert ist, ihm jedoch keine Benutzerrichtlinie und dem Standort des Benutzers keine Standortrichtlinie zugewiesen wurde, wird die globale Richtlinie angewendet. Die globale Richtlinie wird mit lync Server 2013 installiert. Sie können diese Richtlinie Ihren Anforderungen entsprechend ändern, Sie können sie jedoch weder umbenennen noch löschen.

  - Eine *Standortrichtlinie* kann sich auf alle Benutzer auswirken, die an dem Standort verwaltet werden, für den die Richtlinie definiert wurde. Wenn ein Benutzer für den Zugriff auf gehostete Exchange UM-Dienste konfiguriert ist, ihm jedoch keine Benutzerrichtlinie zugewiesen wurde, findet die Standortrichtlinie Anwendung.

  - Eine *Benutzerrichtlinie* kann sich nur auf einzelne Benutzer oder Benutzergruppen auswirken. Zum Erzwingen einer Richtlinie auf Benutzerebene müssen Sie die Richtlinie explizit auf einzelne Benutzer, Gruppen oder Kontaktobjekte anwenden.

<div>


> [!NOTE]  
> In den meisten Fällen ist nur eine Richtlinie für gehostete Voicemail erforderlich. Häufig können Sie die globale Richtlinie ändern, um alle Anforderungen zu erfüllen. Wenn Sie mehrere Richtlinien für gehostete Voicemail bereitstellen, gelten alle diese Richtlinien auf Benutzerebene.



</div>

</div>

<div>

## <a name="hosted-voice-mail-policy-attributes"></a>Attribute einer Richtlinie für gehostete Voicemail

Eine VoIP-Richtlinie definiert zwei Attribute, die die lync Server 2013 ExUM-Routing Anwendung in den Anforderungs-URI einer INVITE-Nachricht einfügt, die an die gehostete Exchange um-Implementierung gesendet wird:

  - **Ziel:** Der vollqualifizierte Domänenname (FQDN) des gehosteten Exchange um Diensts. Dieser Wert wird vom lokalen lync Server Edgeserver für Routingzwecke verwendet.
    
    <div>
    

    > [!NOTE]  
    > Der FQDN (Fully Qualified Domain Name, vollqualifizierter Domänenname) für Exchange Online lautet exap.um.outlook.com.

    
    </div>

  - **Organisation:** Der FQDN des Mandanten im gehosteten Exchange um Dienst, der die Postfächer der lync Server 2013-Benutzer beherbergt. Eine Voicemailrichtlinie kann mehrere Organisationen umfassen. Wenn in der Richtlinie mehr als eine Organisation enthalten ist, muss es sich bei diesem Attribut um eine durch trennzeichengetrennte Liste der Exchange Server Mandanten handeln, die ihre lync Server 2013 Benutzerpostfächer zu Hause sind.

<div>


> [!NOTE]  
> Der Administrator für Mandanten Ihres gehosteten Exchange UM-Diensts stellt die erforderlichen Werte für die Einstellungen der Attribute "Destination" und "Organization" bereit. Zum Erstellen und Konfigurieren einer neuen Richtlinie müssen Sie das Cmdlet "New-CsHostedVoicemailPolicy" ausführen. Wenn Sie eine vorhandene Richtlinie (z. B. die globale Richtlinie) ändern möchten, verwenden Sie das Cmdlet "Set-CsHostedVoicemailPolicy".



</div>

Ausführliche Informationen zum Verwalten von Richtlinien für gehostete Voicemail finden Sie in der lync Server-Verwaltungsshell-Dokumentation für die folgenden Cmdlets:

  - New-CsHostedVoicemailPolicy

  - Gruppe-CsHostedVoicemailPolicy

  - Get-CsHostedVoicemailPolicy

</div>

<div>

## <a name="per-user-voice-mail-policy-assignment"></a>Zuweisen von Richtlinien auf Benutzerebene

Wenn Ihre Richtlinien für gehostete Voicemail auf Benutzerebene definiert sind, müssen Sie diese explizit zuweisen. Sie können das Cmdlet "Grant-CsHostedVoicemailPolicy" ausführen, um die Richtlinie einzelnen Benutzern oder Gruppen zuzuweisen.

Ausführliche Informationen zum Zuweisen oder Entfernen einer Richtlinie für gehostete Voicemail auf Benutzerbasis finden Sie in der lync Server-Verwaltungsshell-Dokumentation für die folgenden Cmdlets:

  - Grant-CsHostedVoicemailPolicy

  - Remove-CsHostedVoicemailPolicy

</div>

</div>

<span> </span>

</div>

</div>

</div>

