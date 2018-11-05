---
title: Ausführen der Abwärtskompatibilität für den Server für beständigen Chat
TOCTitle: Ausführen der Abwärtskompatibilität für den Server für beständigen Chat
ms:assetid: 53f1a706-3104-4a94-8b4e-8badd9a066d6
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204901(v=OCS.15)
ms:contentKeyID: 49294016
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ausführen der Abwärtskompatibilität für den Server für beständigen Chat

 

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Der Server für beständigen Chat-Endpunkt von Lync Server 2013 ermöglicht das Erstellen einfacher URLs, die auf einen Serverpool für beständigen Chat zeigen. Dies ist hilfreich für Clients von Vorversionen wie ( Microsoft Office Communications Server 2007 R2Gruppenchatserver oder Lync Server 2010-Gruppenchat), da Benutzer bei der manuellen Konfiguration einfach eine URL eingeben können, damit der Client der Vorversion auf einen Computer mit Lync 2013Beständiger Chat zeigt. Dieser Endpunkt wird von Beständiger Chat nicht verwendet. Er ist nur für Clients von Vorversionen erforderlich. Diese Vorgehensweise ist hilfreich für den Übergangszeitraum, wenn Räume möglicherweise migriert werden müssen, die Lync 2013-Clients jedoch noch nicht in der gesamten Organisation bereitgestellt wurden. Benutzer mit Lync 2010Gruppenchat (Client) können weiterhin eine Verbindung mit dem Server für beständigen ChatBack-End-Server herstellen.

Es ist nicht erforderlich, mehrere Server für beständigen Chat-Endpunkte zu erstellen. Je Serverpool für beständigen Chat ist ein Endpunkt ausreichend. Administratoren können mehrere Endpunkte (einen pro Pool) erstellen. Clients von Vorversionen können jedoch nur jeweils eine Verbindung zu einem Pool herstellen. In einem üblichen Szenario umfasst eine Bereitstellung für Vorversionen nur einen Pool. Bei einer neuen Bereitstellung wird dieser Pool i. d. R. zu einem neuen Lync Server 2013 migriert, und einige zusätzliche Serverpools für beständigen Chat können hinzugefügt werden.

Übliche Szenarien weisen i. d. R. folgendes Muster auf:

  - Die Benutzer werden mit einem Lync Server 2010-Gruppenchat-Pool verwaltet, und die Lync 2010-Gruppenchat-Clients stellen die Verbindung zu dem Pool mit einem bekannten Benutzer (wie dem Standardbenutzer sip:ocschat@ *\<Domänenname\>* .com) oder einem ähnlichen Benutzer her. Die Benutzer wurden für SIP und Active Directory-Domänendienste aktiviert und werden vom Suchdienst für den Empfang von eingehenden Anforderungen registriert.

  - Anschließend installieren Sie einen Lync Server 2013Server für beständigen Chat und einen Serverpool für beständigen Chat.

  - Für den Zeitraum, in dem die Benutzer für gewöhnlich offline sind (z. B. am Wochenende) werden folgende Maßnahmen empfohlen:
    
      - Deaktivieren Sie den Lync Server 2010-Gruppenchat.
    
      - Migrieren Sie Daten vom Lync Server 2010-Gruppenchat-Pool zum Lync Server 2013Serverpool für beständigen Chat.
    
      - Löschen Sie den bekannten Benutzer aus dem Active Directory-Domänendienste.
    
      - Erstellen Sie einen neuen *Endpunkt für Vorversionen* mit dem gleichen SIP-URI wie für den zuvor gelöschten bekannten Benutzer.
    
      - Starten Sie die Server für beständigen Chat von Lync Server 2013.

  - Die Benutzer melden sich wieder mit dem Lync 2010-Gruppenchat-Client an und stellen eine Verbindung zu Ihren Daten her, ohne Änderungen an der Konfiguration vornehmen zu müssen.

  - Die alte Bereitstellung von Lync Server 2010-Gruppenchat kann zu einem späteren Zeitpunkt außer Betrieb genommen werden. Anschließend können Sie Lync Server 2013Server für beständigen Chat bereitstellen und neue Lync Server 2013Serverpools für beständigen Chat installieren.

Nähere Informationen zur Migration von Lync Server 2010-Gruppenchat zu Lync Server 2013Server für beständigen Chat finden Sie unter [Migration von Lync Server 2010-Gruppenchat oder Office Communications Server 2007 R2-Gruppenchat zu Lync Server 2013 Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).

Gehen Sie wie folgt vor, um die Abwärtskompatibilität herzustellen (und einen Server für beständigen Chat-Endpunkt zu erstellen, der auf einen Serverpool für beständigen Chat verweist, der von den Gruppenchat-Poolclients von Vorversionen verwendet werden kann):

    New-CsPersistentChatEndpoint -SipAddress <CO name, ex. persistentchat@contoso.com> -PersistentChatPoolFqdn <pool FQDN, like pcpool.contoso.com>

Als Nächstes konfigurieren Sie Beständiger Chat-Clients zur Verwendung dieser SIP-Adresse als Kontaktobjekt. Die SIP-Adresse wird mit dem **New-CsPersistentChatEndpoint**-Cmdlet für einen bestimmten Serverpool für beständigen Chat erstellt.

Im folgenden Beispiel wird veranschaulicht, wie Sie den Server für beständigen Chat-Endpunkt mit Windows PowerShell-Befehlszeilenschnittstelle hinzufügen können. In diesem Fall konfigurieren Sie das Kontaktobjekt und weisen ihm den Namen "persistentchat" für die Topologie "contoso.com" zu, deren vollqualifizierter Pooldomänenname "pcpool.contoso.com" lautet:

    New-CsPersistentChatEndpoint -SipAddress sip:persistentchat@contoso.com -PersistentChatPoolFqdn pcpool.contoso.com

## Siehe auch

#### Konzepte

[Migration von Lync Server 2010-Gruppenchat oder Office Communications Server 2007 R2-Gruppenchat zu Lync Server 2013 Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)

