---
title: 'Lync Server 2013: Routing für gehostete Exchange UM-Dienste'
TOCTitle: Routing für gehostete Exchange UM-Dienste
ms:assetid: 6c90dc8b-6aef-4ce8-b483-37c7b5a553c2
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398512(v=OCS.15)
ms:contentKeyID: 49294321
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Routing für gehostete Exchange UM-Dienste in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-01_

Die Exchange UM-Routinganwendung wird auf dem Front-End-Server für die Weiterleitung von Anrufen an eine lokale Microsoft Exchange Server Unified Messaging-Bereitstellung (UM) oder an gehostete Exchange UM-Dienste ausgeführt.

## Die ExUM-Routinganwendung

Die Lync Server 2013Exchange UM-Routinganwendung verwendet Informationen aus Benutzerkontoeinstellungen und Parameter einer gehosteten VoIP-Richtlinie, um zu ermitteln, wie Anrufe für gehostetes Voicemessaging weitergeleitet werden (wie in der folgenden Abbildung gezeigt).

**Beispiel für das Exchange UM-Routing in einer gemischten Bereitstellung**

![Lokale Lync Server-Exchange UM-Bereitstellung](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "Lokale Lync Server-Exchange UM-Bereitstellung")

Das Exchange UM-Routing kann für das Weiterleiten von Anrufen an Benutzer konfiguriert werden, die für lokale Exchange UM-Dienste oder für gehostete Exchange UM-Dienste bzw. für eine Kombination der beiden Diensttypen aktiviert sind.

Gehen wir z. B. davon aus, dass sich das Postfach und der Exchange UM-Dienst des Benutzers Roy in einer lokalen Exchange-Bereitstellung befinden.

  - Die Proxyadressinformationen aus dem Benutzerkonto von Roy liefern die Informationen, welche die ExUM-Routinganwendung zum Weiterleiten der Anrufe dieses Benutzers an einen lokalen Exchange UM-Server verwendet.

Das Postfach und der Exchange UM-Dienst der Benutzerin Alice befinden sich im Rechenzentrum eines Anbieters gehosteter Exchange-Dienste. Das Routing für ihre Exchange UM-Anrufe wird wie folgt konfiguriert:

  - Die im Attribut "msExchUCVoiceMailSettings" des Benutzerkontos von Alice festgelegten Werte weisen die ExUM-Routinganwendung an, eine gehostete Voicemailrichtlinie auf Routingdetails zu überprüfen.
    

    > [!NOTE]
    > Der Wert des Attributs "msExchUCVoiceMailSettings" kann entweder durch den Exchange-Dienstanbieter oder durch den Lync Server 2013-Administrator festgelegt werden. Im oben gezeigten Beispiel wurde der Wert (CsHostedVoiceMail=1) vom Lync Server 2013-Administrator gesetzt, um gehostete Voicemail für Alice zu aktivieren. Ausführliche Informationen zu diesem Attribut finden Sie unter <A href="lync-server-2013-hosted-exchange-user-management.md">Benutzerverwaltung für gehostete Exchange-Dienste in Lync Server 2013</A>.



  - Die dem Benutzerkonto von Alice zugewiesene gehostete Voicemailrichtlinie umfasst Routingdetails:
    
      - Das Ziel ist der Dienstanbieter für gehostete Exchange UM-Dienste ("ls.ExUm. *\<gehosteter Exchange-Server\>* .com" in diesem Beispiel).
    
      - Organisationen werden durch die Mandanten-IDs identifiziert, bei denen es sich um die Routing-FQDNs für SIP-Nachrichten für Exchange Server-Mandanten auf "ls.ExUm. *\<gehosteter Exchange-Server\>* .com" handelt (in diesem Beispiel "corp.contoso.com" und "corp.litwareinc.com").
        

        > [!NOTE]
        > Der FQDN für Exchange Online ist exap.um.outlook.com .

        
        Ausführliche Informationen finden Sie unter [Richtlinien für gehostete Voicemail in Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md).


> [!NOTE]
> Wenn sowohl das Attribut "msExchUCVoiceMailSettings" als auch die UM-Proxyadresseinstellungen in einem Benutzerkonto vorhanden sind, hat das Attribut "msExchUCVoiceMailSettings" Vorrang.


