---
title: 'Lync Server 2013: Übersicht über den Zugriff durch externe Benutzer'
TOCTitle: Übersicht über den Zugriff durch externe Benutzer
ms:assetid: 97aded6c-5fa3-4225-95a6-9ad094d61654
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398775(v=OCS.15)
ms:contentKeyID: 49294833
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Übersicht über den Zugriff durch externe Benutzer in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

In dieser Dokumentation wird der Begriff *externer Benutzer* zur Definition einer großen Kategorie von Benutzern verwendet, die mit Ihrem Lync Server 2013 kommunizieren, und von Lync 2013-Benutzern von außerhalb der Firewall. Zu den externen Benutzern, die Sie für die Verwendung von Lync Server 2013 zur Kommunikation mit internen Benutzern autorisieren können (also mit Benutzern, die sich innerhalb der Firewall bei Lync Server anmelden), gehören beispielsweise Folgende:

  - **Remotebenutzer**   Benutzer Ihrer Organisation, die sich von außerhalb der Firewall bei Lync Server anmelden.

  - **Partnerbenutzer**   Benutzer, die ein Konto bei einer als vertrauenswürdig eingestuften Kunden- oder Partnerorganisation haben, wie Lync Server 2010, Lync Server 2013 oder Office Communications Server 2007 R2. Partnerbenutzer können auch Benutzer definierter Partnerorganisationen sein, die XMPP über den XMPP-Proxy auf dem Edgeserver und das XMPP-Gateway auf dem Front-End-Server oder im Pool verwenden. Eine definierte vertrauenswürdige Beziehung, also ein Verbund, hat keinen Bezug zu einer vertrauenswürdigen Active Directory-Domänendienste-Beziehung und ist davon nicht abhängig.
    

    > [!NOTE]
    > Für AOL und Yahoo! wurde die Einstellung des Diensts für Juni 2014 angekündigt. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Unterstützen von Verbindungen mit öffentlichen Chatdiensten in Lync Server 2013</A>.



  - **Benutzer mit Verbindung mit öffentlichen Instant Messaging-Diensten**   Kontakte, die Ihre Benutzer über Verbindungen mit öffentlichen Instant Messaging-Diensten (Windows Live, Yahoo\! und AOL) herstellen.

  - **Mobilbenutzer**   Benutzer, die Mitglieder Ihrer Organisation sind und ein Smartphone oder Tablet benutzen, auf dem ein Lync Mobile-Client ausgeführt wird. Diese melden sich bei Ihrer internen Bereitstellung an und können mit den anderen Benutzerklassen kommunizieren. Mobilbenutzer nutzen Mobildienste, die über den Reverseproxy veröffentlicht werden, um auf die interne Bereitstellung zuzugreifen. Ausführliche Informationen zu den in Lync Mobile verfügbaren Funktionen und Möglichkeiten finden Sie in den Mobil-Client-Vergleichstabellen unter [http://go.microsoft.com/fwlink/?linkid=234777\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=234777%26clcid=0x407).

  - **Anonyme Benutzer**   Benutzer, die nicht über ein Benutzerkonto in Active Directory-Domänendienste Ihrer Organisation oder in einer unterstützten Partnerdomäne verfügen, die jedoch zur Remoteteilnahme an einer lokalen Konferenz eingeladen werden.

Ihre Edgebereitstellung bietet externen Zugriff für folgende Kommunikationstypen:

  - **Chatnachrichten und Anwesenheit**   Autorisierte externe Benutzer können an Chatnachrichtenunterhaltungen und -konferenzen teilnehmen sowie Informationen über den Anwesenheitsstatus anderer Benutzer abrufen. Benutzer öffentlicher Instant Messaging-Dienstanbieter können an Chatnachrichtenunterhaltungen mit einzelnen Lync Server-Benutzern in Ihrer Organisation teilnehmen und auf Anwesenheitsinformationen zugreifen, aber nicht an Chatnachrichtenkonferenzen über den Lync Server teilnehmen, an denen mehrere Personen beteiligt sind. Die Konferenzfunktion kann ausschließlich als Peer-zu-Peer-Option genutzt werden. Dateitransfer wird für Benutzer öffentlicher Instant Messaging-Dienstanbieter nicht unterstützt. Audio/Video in Peer-zu-Peer-Kommunikation wird für Benutzer von Windows Messenger 2011 unterstützt, aber nicht für andere Benutzer öffentlicher Instant Messaging-Dienstanbieter.
    
    Es wird sowohl das SIP- als auch das XMPP-Protokoll unterstützt. Informationen zur Bereitstellung von Diensten für XMPP finden Sie unter [Planen für SIP-, XMPP-Partnerverbund und öffentliche Chats in Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md).

  - **Webkonferenzen**   Autorisierte externe Benutzer können an Konferenzen teilnehmen, die in Ihrer Lync Server-Bereitstellung gehostet werden. Remotebenutzern, Verbundbenutzern und anonymen Benutzern kann die Teilnahme an Webkonferenzen ermöglicht werden, Benutzer öffentlicher Instant Messaging-Dienste können jedoch nicht an Konferenzen teilnehmen. Je nach den ausgewählten Optionen können für Webkonferenzen aktivierte Benutzer an der Desktop- und Anwendungsfreigabe teilnehmen und als Besprechungsorganisatoren oder Referenten agieren.

  - **A/V-Konferenzen**   Autorisierte externe Benutzer können an Audio- und Videokonferenzen teilnehmen, die von Ihrer Lync Server-Bereitstellung gehostet werden. Audio/Video in Peer-zu-Peer-Kommunikationen werden für Benutzer von Windows Messenger 2011, aber nicht für andere Benutzer öffentlicher Chatanbieter unterstützt.

Zum Steuern der Kommunikation können Sie eine oder mehrere Richtlinien konfigurieren, durch die definiert wird, wie Benutzer innerhalb und außerhalb der Firewall miteinander kommunizieren. Außerdem können Sie für einzelne interne Benutzer oder für bestimmte Typen externer Benutzer Einstellungen konfigurieren und Richtlinien anwenden, um die Kommunikation mit externen Benutzern zu steuern.

Lync Server 2013-Rollen, die für den Zugriff externer Benutzer verwendet werden:

**Edgeserver**   Der Edgeserver ist ein Server oder ein Pool von Servern, auf dem Dienste ausgeführt werden, die den externen Zugriff auf Instant Messaging- und Anwesenheits-, Konferenz-, Audio/Video- und andere Mediendienste (z. B. Dateiübertragung) ermöglichen. Optional können Sie den Edgeserver konfigurieren, um einen Verbund mit anderen Lync Server- oder Office Communications Server 2007 R2-Bereitstellungen und anderen XMPP-Bereitstellungen herzustellen. Die optionale Funktion für öffentliche Instant Messaging-Verbindungen wird über den Edgeserver aktiviert und konfiguriert.

**Director**   Der Director ist ein optionaler Server oder Serverpool, auf dem der Lync Server 2013- Director ausgeführt wird, der Benutzeranfragen im Vorfeld authentifiziert und Anfragen an den Front-End-Server oder den Front-End-Pool des Benutzers weiterleitet, aber keine Benutzerkonten besitzt.

**Reverseproxy**   Ein Reverseproxy ist ein allgemeiner Begriff für spezialisierte Server, die Ressourcen veröffentlichen, die im internen Netzwerk verfügbar sind, und für Clients Informationen aus der veröffentlichten Ressource abrufen. Lync Server 2013 nutzt den Reverseproxy für die Veröffentlichung diverser Funktionen, wie Konferenzbesprechungen, Konferenzbeitrittsorte, das Adressbuch, die Verteilerlistenerweiterung, das Herunterladen von Besprechungsinhalten, Geräteaktualisierungen, Mobildienste und weitere. Es kann jeder Reverseproxy verwendet werden, der die Anforderungen für die Veröffentlichung der erforderlichen Ressourcenspeicherorte erfüllt. Zur Verdeutlichung der erforderlichen Veröffentlichungsregeln wird hier Microsoft Forefront Threat Management Gateway (TMG) 2010 genutzt, Forefront TMG 2010 ist allerdings nicht erforderlich.


> [!IMPORTANT]
> Lync Server 2013 unterstützt IPv4 und IPv6. Windows Server&nbsp;2008&nbsp;R2, Windows Server 2012 und Windows Server 2012 R2 nutzen einen dualen Stapel, der sowohl IPv4 als auch IPv6 gleichzeitig verwenden kann. Dies ist aufgrund des Übergangsstatus einer Bereitstellung wichtig, die von IPv4 auf IPv6 umgestellt wird. In einigen Bereichen kann IPv4 unterstützt werden, während in anderen Bereichen der Bereitstellung IPv6 eingesetzt wird. Dies ist insbesondere dort wichtig, wo das Internet und interne Bereitstellungen betroffen sind. Externe Clients müssen über den Reverseproxy kommunizieren, um Dienste wie Mobilität, Besprechungen, Adressbuch-Download und andere zu nutzen. Forefront Threat Management Gateway 2010 und Internet Security and Acceleration Server 2006 unterstützen zurzeit keine IPv6-Adressierung - unabhängig von der Betriebssystemversion, auf der sie bereitgestellt werden. Entsprechend müssen Sie die Verwendung von IPv6 und IPv4 planen, wenn es um externe Clients geht.


