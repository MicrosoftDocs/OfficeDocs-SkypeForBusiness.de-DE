---
title: 'Lync Server 2013: Topologien und Komponenten für Mobilität'
TOCTitle: Topologien und Komponenten für Mobilität
ms:assetid: be3cae7a-095d-4785-91ba-6fac99eba92a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Hh690037(v=OCS.15)
ms:contentKeyID: 49295257
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Topologien und Komponenten für Mobilität in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-17_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Für die Unterstützung der mobilen Lync-Anwendungen auf mobilen Geräten bietet Lync Server 2013 drei verschiedene Dienste: den Mcx-Mobilitätsdienst, den AutoErmittlungsdienst und den Pushbenachrichtungsdienst. Im Rahmen der kumuliativen Updates für Lync Server 2013 aus dem Februar 2013 ist ein kostenloser, aber ausgereifter Dienst für mobile Clients von Lync 2013 hinzugekommen, der Unterstützung von Mobilität durch die Nutzung des Unified Communications-Web-API (UCWA) ermöglicht. In diesem Abschnitt werden diese Komponenten kurz beschrieben. Außerdem werden Lync Server 2013-Topologien zur Unterstützung von Mobilität vorgestellt.


> [!NOTE]
> Mobilitätsdienste sind auch in hybriden Bereitstellungen verfügbar. Sie müssen keine Dienste zur Unterstützung der Mobilität bereitstellen, falls die Benutzer online verwaltet werden. Sie müssen eine Einstellung für den AutoErmittlungsdienst definieren, damit mobile Benutzer ihre Onlineidentität auffinden können.




> [!IMPORTANT]
> Falls Sie Konnektivität für externe Benutzer planen (z.&nbsp;B. Partnerverbund, externer Benutzerzugriff oder Mobilitätsfeatures), müssen Sie Edgeserver mit Standard Edition-Server und dem Front-End-Server oder Front-End-Pool verwenden. Der Standard Edition-Server und der Front-End-Server oder Front-End-Pool verfügen nicht über die erforderlichen Komponenten, um externen Benutzern den Zugriff auf Ihre interne Bereitstellung bzw. der internen Bereitstellung die Kommunikation mit Ihren externen Benutzern zu erlauben. Für alle Szenarien, bei denen externe Benutzer mit internen Benutzern zusammenarbeiten oder kommunizieren, einschließlich der Mobilität, müssen Sie mindestens einen Edgeserver und einen Reverseproxy bereitstellen.<BR>Die <EM>Pushbenachrichtigung</EM> verwendet einen Partnerverbundtyp für Lync Online-Dienste, von dem PNCH (Push Notification Clearing House) gehostet wird. Die Pushbenachrichtigung bezeichnet die akustischen Signale, Warnungen auf dem Bildschirm (Text) und Signale, die von Anwendungen an Apple iPhone, iPad und Windows Phone weitergeleitet werden, wenn das mobile Gerät inaktiv ist. PNCH empfängt Pushbenachrichtigungen von Lync Server. Wenn PNCH eine Benachrichtigung über eine Nachricht empfängt, leitet das PNCH über die Apple-Pushbenachrichtigungsdienste oder den Lync Server 2013-Pushbenachrichtigungsdienst eine Benachrichtigung an mobile Clients weiter, und zwar basierend auf dem mobilen Client, für den die Nachricht gedacht ist. PNCH ist ein erforderlicher Dienst für diese mobile Clients. Für den Partnerverbund mit Lync Online verwendet PNCH Edgeserver und Zertifikate, um Vertraulichkeit und Authentifizierung, Richtlinien sowie ordnungsgemäß konfigurierte DNS-Einträge (Domain Name System) sicherzustellen. Nokia Symbian und Android-basierte Lync Mobile-Clients verwenden PNCH nicht. Ausführliche Informationen zum Planen und Bereitstellen von Edgeserver finden Sie unter <A href="lync-server-2013-planning-for-external-user-access.md">Planen des Zugriffs externer Benutzer in Lync Server 2013</A> und <A href="lync-server-2013-deploying-external-user-access.md">Bereitstellen des Zugriffs durch externe Benutzer in Lync Server 2013</A>.<BR>Die mobilen Lync 2013-Clients für Apple-Geräte, die mit den im Februar 2013 veröffentlichten kumulativen Updates für Lync Server 2013 eingeführt wurden, verwenden Pushbenachrichtigungen oder das Push Notification Clearing House (PNCH) nicht mehr. Mobile Lync 2013-Clients auf dem Windows Phone verwenden immer noch Pushbenachrichtigungen und das PNCH.



## Mobilitätskomponenten

Die folgenden Dienste unterstützen Mobilität:

  - **Lync Server 2013-UCWA (Unified Communications Web API)**   Stellt Dienste für die Echtzeitkommunikation mit mobilen und Webclients in Lync Server 2013 bereit. Wenn Sie die im Februar 2013 bereitgestellten kumulativen Updates für Lync Server 2013 auf dem Front-End-Server und Director bereitstellen, wird bei der Installation ein virtuelles Verzeichnis in den internen und externen Webdiensten ("Ucwa") erstellt. Eine Webkomponente, die Teil des virtuellen Verzeichnisses "Ucwa" ist, akzeptiert Anrufe von UCWA-fähigen Clients. Die Client-Apps kommunizieren über eine REST-Schnittstelle, um Anwesenheit, Kontakte, Chat, VoIP, Videokonferenzen und Zusammenarbeit zu ermöglichen. UCWA verwendet einen P-GET-basierten Kanal, um Ereignisse zu senden, z. B. eingehende Anrufe, eingehende Chatnachrichten oder Nachrichten für die Client-App.
    

    > [!NOTE]
    > <EM>REST</EM> oder Representational State Transfer ist ein Softwarearchitekturstil für verteilte Systeme, der in vielen Formen breite Anwendung findet und sich im Allgemeinen gut für die Anforderungen von Webdiensten eignet.



  - **Lync Server 2013-Mobilitätsdienst (Mcx)**   Dieser Dienst unterstützt Lync-Funktionen, z. B. Chat, Anwesenheit und Kontakte, auf mobilen Geräten. Der Mobilitätsdienst wird auf jedem Front-End-Server in allen Pools installiert, die Lync-Funktionen auf mobilen Geräten unterstützen sollen. Bei der Installation von Lync Server 2013 wird ein neues virtuelles Verzeichnis ("Mcx") sowohl unter der internen Website als auch unter der externen Website auf den Front-End-Servern erstellt.
    

    > [!IMPORTANT]
    > Lync Server 2013 mit den kumulativen Updates für Lync Server 2013 vom Februar 2013 unterstützt sowohl den Mobilitätsdienst, der mit dem kumulativen Update für Lync Server 2010 vom November 2011 eingeführt wurde und allgemein als Mcx bekannt ist, als auch die UCWA-Webkomponente. Die Kombination dieser beiden Mobilitätsdienste bietet Interoperabilität und ermöglicht, dass die Dienste von Benutzern genutzt werden können, die mobile Lync 2010 Mobile- und Lync 2013-Clients in Lync Server 2013 verwenden.



  - **Lync Server 2013 AutoErmittlungsdienst**   Dieser Dienst ermittelt den Standort des Benutzers und versetzt mobile Geräte und andere Clients von Lync in die Lage, unabhängig vom Netzwerkstandort nach Ressourcen zu suchen, z. B. nach internen und externen URLs von Lync Server 2013-Webdiensten und der URL für Mcx oder UCWA. Für die automatische Ermittlung werden hartcodierte Hostnamen ("lyncdiscoverinternal" für Benutzer innerhalb des Netzwerks und "lyncdiscover" für Benutzer außerhalb des Netzwerks) und die SIP-Domäne des Benutzers verwendet. Sowohl Clientverbindungen über HTTP als auch HTTPS werden unterstützt.
    
    Der AutoErmittlungsdienst wird auf allen Front-End-Servern und auf allen Directors in jedem Pool installiert, der die Lync-Funktionen auf mobilen Geräten unterstützen soll. Wenn Sie den AutoErmittlungsdienst installieren, wird ein neues virtuelles Verzeichnis ("Autodiscover") sowohl unter der internen Website als auch unter der externen Website auf den Front-End-Servern und Directorss installiert.
    

    > [!NOTE]
    > Der AutoErmittlungsdienst ist hier aufgelistet, da er bei der Bereitstellung von Clientdiensten weiterhin eine wichtige Komponente bleibt. Die Rolle der AutoErmittlung in Lync Server 2013 wurde erweitert, um Dienste für alle Clients bereitzustellen. Ausführliche Informationen zur Planung des AutoErmittlungsdiensts finden Sie unter <A href="lync-server-2013-planning-for-autodiscover.md">Planen der AutoErmittlung in Lync Server 2013</A>.



  - **Pushbenachrichtigungsdienst**   Ein cloudbasierter Dienst, der über das Lync Online-Rechenzentrum gehostet wird. Wenn eine mobile Lync-Anwendung auf einem unterstützten Apple iOS- oder Windows Phone-Gerät inaktiv ist, kann es nicht auf neu eintretende Ereignisse, z. B. eine neue Instant Messaging-Einladung, eine verpasste Instant Messsage, einen verpassten Anruf oder eine Voicemail, reagieren, da die Geräte das Ausführen von Anwendungen im Hintergrund nicht unterstützen. In einem solchen Fall wird eine Benachrichtigung über das Ereignis, eine so genannte *Pushbenachrichtigung*, an das mobile Gerät gesendet. Der Mobilitätsdienst sendet die Benachrichtigung an den cloudbasierten Pushbenachrichtigungsdienst, der diese dann entweder an den Apple Push Notification Service (APNS) (bei unterstützten Apple iOS-Geräten) oder an den Microsoft Push Notification Service (MPNS) (bei Windows Phone) weiterleitet, der dann den Transport zum Endgerät übernimmt. Der Benutzer kann dann auf die Benachrichtigung auf seinem mobilen Gerät reagieren, um die Anwendung zu aktivieren.
    
    Lync 2010 Mobile auf Apple- und Windows Phone-Geräten verwendet Pushbenachrichtigungen. Der mobile Lync 2013-Client für Apple-Geräte, der mit den kumulativen Updates für Lync Server 2013 vom Februar 2013 eingeführt wurde, verwendet Pushbenachrichtigungen oder das Push Notification Clearing House (PNCH) nicht mehr.

Die folgende Abbildung zeigt, wie der Pushbenachrichtigungsdienst sich in eine Lync Server 2013-Topologie einfügt, in der UCWA und mobile Lync 2013-Clients verwendet werden.

![Pushbeachrichtigungsdienste UCWA](images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "Pushbeachrichtigungsdienste UCWA")

Der Mcx-Dienst, der mit dem kumulativen Update für Lync Server 2010 vom November 2011 eingeführt wurde, stellt Dienste für Lync 2010 Mobile-Clients bereit. Das folgende Diagramm veranschaulicht den Pushbenachrichtigungsdienst, der in einer Topologie mit dem Mcx-Dienst und Lync 2010 Mobile-Clients eingesetzt wird.

![Pushbeachrichtigungsdienste MCX](images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "Pushbeachrichtigungsdienste MCX")

## Unterstützte Topologien

Durch Anwenden der kumulativen Updates für Lync Server 2013 vom Februar 2013 werden die UCWA-Webkomponenten hinzugefügt, um die Mobilität für Features des mobilen Lync 2013-Clients in den folgenden Topologien zu unterstützen:

  - Lync Server 2013  Standard Edition

  - Lync Server 2013 Enterprise Edition

Der Edgeserver kann ein Lync Server 2010- Edgeserver sein.

Eine Lync Server 2013-Bereitstellung ohne die kumulativen Updates für Lync Server 2013 vom Februar 2013 verwendet den Mcx-Mobilitätsdienst und stellt nur Dienste für Lync 2010 Mobile bereit.


> [!IMPORTANT]
> Der Mobilitätsdienst wird auf Front-End-Servern unterstützt, die über die Vermittlungsserverrolle mit zwei Netzwerkschnittstellen verbunden sind. Es sind aber entsprechende Schritte erforderlich, um die Schnittstellen zu konfigurieren. Sie müssen die IP-Adressen der spezifischen Schnittstelle zuweisen, die als Vermittlungsserver kommuniziert, sowie die Netzwerkschnittstellen-IP, die als Front-End-Server kommuniziert. Sie können diese Zuordnung in Topologie-Generator vornehmen, indem Sie die richtige IP-Adresse für jeden Dienst auswählen, anstatt die Standardeinstellung <STRONG>Alle konfigurierten IP-Adressen verwenden</STRONG> zu verwenden.



## Siehe auch

#### Weitere Ressourcen

[Planen des Zugriffs externer Benutzer in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md)  
[Bereitstellen des Zugriffs durch externe Benutzer in Lync Server 2013](lync-server-2013-deploying-external-user-access.md)  
[Planen der AutoErmittlung in Lync Server 2013](lync-server-2013-planning-for-autodiscover.md)

