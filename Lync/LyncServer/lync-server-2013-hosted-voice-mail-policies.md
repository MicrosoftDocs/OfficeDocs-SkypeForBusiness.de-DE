---
title: 'Lync Server 2013: Richtlinien für gehostete Voicemail'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hosted voice mail policies
ms:assetid: d62a35ed-cbe2-4f06-86b4-e192c18435c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398932(v=OCS.15)
ms:contentKeyID: 48185506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a23f5fa67a34d479bbc5b9d5c9bf55071b187c1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832062"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-voice-mail-policies-in-lync-server-2013"></a>Richtlinien für gehostete Voicemail in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-01_

Eine *Richtlinie für gehostete Voicemail* bietet Informationen für die lync Server 2013 ExUM-Routing Anwendung über den Ort, an den Anrufe für Benutzer weitergeleitet werden sollen, deren Postfächer sich in einem gehosteten Exchange-Dienst befinden.

<div>


> [!NOTE]  
> Richtlinien für gehostete Voicemail sind nur für die lync Server 2013-Integration in Hosted Exchange um erforderlich. Sie werden für die Integration in lokale Exchange um nicht benötigt.



</div>

<div>

## <a name="hosted-voice-mail-policy-scope"></a>Richtlinienbereich für gehostete Voicemails

Der Richtlinien-Bereich für gehostete Voicemail bestimmt die hierarchische Ebene, auf der die Richtlinie angewendet wird. Sie können gehostete Voicemail-Richtlinien mit den folgenden Bereichsebenen konfigurieren:

  - Die *globale* Richtlinie kann sich potenziell auf alle Benutzer in der lync Server 2013-Bereitstellung auswirken. Wenn ein Benutzer für den gehosteten Exchange um-Zugriff aktiviert ist und keiner Richtlinie pro Benutzer zugewiesen wurde und eine Website Richtlinie nicht der Website des Benutzers zugewiesen wurde, gilt die globale Richtlinie. Die globale Richtlinie wird mit lync Server 2013 installiert. Sie können Sie ändern, um Ihre Anforderungen zu erfüllen, aber Sie können Sie nicht umbenennen oder löschen.

  - Eine *Website* Richtlinie kann sich auf alle Benutzer auswirken, die sich auf der Website befinden, für die die Richtlinie definiert ist. Wenn ein Benutzer für den gehosteten Exchange um-Zugriff konfiguriert ist und keiner Richtlinie pro Benutzer zugewiesen wurde, gilt die Website Richtlinie.

  - Eine Richtlinie *pro Benutzer* kann sich nur auf einzelne Benutzer oder Gruppen auswirken. Wenn Sie eine Richtlinie pro Benutzer erzwingen möchten, müssen Sie die Richtlinie explizit einzelnen Benutzern, Gruppen und Kontaktobjekten zuweisen.

<div>


> [!NOTE]  
> In den meisten Fällen ist nur eine Richtlinie für gehostete Voicemail erforderlich. Sie können die globale Richtlinie oft so ändern, dass Sie allen Ihren Anforderungen entspricht. Wenn Sie mehrere gehostete Voicemail-Richtlinien bereitstellen, verfügen alle Richtlinien über einen Benutzerbereich.



</div>

</div>

<div>

## <a name="hosted-voice-mail-policy-attributes"></a>Attribute für gehostete Voicemail-Richtlinien

Eine Voicemail-Richtlinie definiert zwei Attribute, die von der lync Server 2013-ExUM-Routing Anwendung in den Anforderungs-URI einer INVITE-Nachricht eingefügt werden, die an die gehostete Exchange um-Implementierung gesendet wird:

  - **Ziel:** Der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des gehosteten Exchange um-Diensts. Dieser Wert wird vom lokalen lync Server-Edgeserver für Routingzwecke verwendet.
    
    <div>
    

    > [!NOTE]  
    > Der FQDN für Exchange Online lautet exap.um.Outlook.com.

    
    </div>

  - **Organisation:** Der FQDN des Mandanten des gehosteten Exchange um-Diensts, in dem die Postfächer ihrer lync Server 2013-Benutzer gespeichert sind. Eine Voicemail-Richtlinie kann mehrere Organisationen enthalten. Wenn in der Richtlinie mehr als eine Organisation enthalten ist, muss dieses Attribut eine durch trennzeichengetrennte Liste der Exchange Server-Mandanten sein, die ihre Benutzerpostfächer in lync Server 2013 verwenden.

<div>


> [!NOTE]  
> Der mandantenadministrator des gehosteten Exchange um-Diensts stellt die erforderlichen Werte für die Attributeinstellungen für Ziel und Organisation bereit. Wenn Sie Ihre Richtlinie konfigurieren möchten, müssen Sie das Cmdlet New-CsHostedVoicemailPolicy ausführen oder das Cmdlet "CsHostedVoicemailPolicy" verwenden, um ein vorhandenes zu ändern (beispielsweise die globale Richtlinie).



</div>

Details zum Verwalten von Richtlinien für gehostete Voicemail finden Sie in der Dokumentation zur lync Server-Verwaltungsshell für die folgenden Cmdlets:

  - Neu – CsHostedVoicemailPolicy

  - Satz-CsHostedVoicemailPolicy

  - Get-CsHostedVoicemailPolicy

</div>

<div>

## <a name="per-user-voice-mail-policy-assignment"></a>Benutzerspezifische Voicemail-Richtlinienzuweisung

Wenn Ihre gehostete Voicemail-Richtlinie mit benutzerdefiniertem Bereich definiert ist, müssen Sie Sie explizit zuweisen. Sie können das Cmdlet Grant-CsHostedVoicemailPolicy ausführen, um die Richtlinie einzelnen Benutzern oder Gruppen zuzuweisen.

Details zum Zuweisen oder Entfernen einer pro Benutzer gehosteten Voicemail-Richtlinie finden Sie in der Dokumentation zur lync Server-Verwaltungsshell für die folgenden Cmdlets:

  - Grant-CsHostedVoicemailPolicy

  - Remove-CsHostedVoicemailPolicy

</div>

</div>

<span> </span>

</div>

</div>

</div>

