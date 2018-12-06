---
title: 'Lync Server 2013: Konfigurieren von Einstellungen für die Voicemailumleitung'
TOCTitle: Konfigurieren von Einstellungen für die Voicemailumleitung
ms:assetid: 7ab6be28-eabb-4a79-a796-648887d71b83
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398606(v=OCS.15)
ms:contentKeyID: 49294494
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Einstellungen für die Voicemailumleitung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-18_

Survivable Branch-Anwendungen und Survivable Branch-Server können während eines WAN-Ausfalls grundlegende VoIP-Funktionen für Zweigstellenbenutzer bieten, wenn Exchange Unified Messaging (UM) am zentralen Standort installiert ist und eine automatische Exchange UM-Telefonzentrale bereitgestellt wurde. Ihr Exchange-Administrator sollte die automatische Telefonzentrale so konfigurieren, dass ausschließlich Nachrichten akzeptiert werden. Dadurch werden andere allgemeine Funktionen (z. B. die Weiterleitung an einen Benutzer oder Agent) deaktiviert. Alternativ können Sie eine allgemeine automatische Telefonzentrale oder eine angepasste automatische Telefonzentrale zur Weiterleitung des Anrufs verwenden.

Ausführliche Informationen finden Sie unter „Vorbereiten der Ausfallsicherheit für VoIP-Funktionen“ unter [Anforderungen für die Ausfallsicherheit an Zweigstellenstandorten für Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md) in der Planungsdokumentation.

## So konfigurieren Sie die Ausfallsicherheit für VoIP-Funktionen

1.  Bitten Sie Ihren Exchange-Administrator, die automatische Telefonzentrale über das folgende Cmdlet in der Exchange-Shell so zu konfigurieren, dass lediglich Nachrichten akzeptiert werden. **Set-UMAutoAttendant \<AA name\> -CallSomeoneEnabled $false**. Der Parameter, der das Hinterlassen von Nachrichten zulässt ( *SendVoiceMsgEnabled*), ist standardmäßig auf „True“ gesetzt.

2.  Verwenden Sie in der Lync Server-Verwaltungsshell das Cmdlet **New-CSVoiceMailReroutingConfiguration**, um die Rufnummer der automatischen Telefonzentrale als Rufnummer der automatischen Exchange UM-Telefonzentrale in der Konfiguration für die Voicemailumleitung der Survivable Branch-Anwendung oder des Survivable Branch-Servers festzulegen.
    

    > [!NOTE]
    > Wenn Sie die Voicemailumleitungseinstellungen ändern müssen, verwenden Sie das Cmdlet <STRONG>Set-CsVoiceMailReRoutingConfiguration</STRONG>. Ausführliche Informationen zu den Cmdlets <STRONG>New-</STRONG> und <STRONG>Set-CSVoiceMailReroutingConfiguration</STRONG> finden Sie in den Hilfethemen der Shell.



3.  Legen Sie die Exchange UM-Teilnehmerzugriffsnummer der Exchange UM-Wähleinstellungen des Zweigstellenbenutzers als Exchange UM-Teilnehmerzugriffsnummer in der Konfiguration für die Voicemailumleitung der Survivable Branch-Anwendung oder des Survivable Branch-Servers fest.
    

    > [!NOTE]
    > Konfigurieren Sie die Exchange UM-Wähleinstellungen des Benutzers so, dass sämtlichen Zweigstellenbenutzern, die während eines WAN-Ausfalls auf die Funktionen zum Abrufen von Voicemail zugreifen müssen, nur ein Satz mit Wähleinstellungen zugeordnet ist.



**Nächster Schritt** für Survivable Branch-Anwendungen oder Survivable Branch-Server: [Verwalten von Benutzern in einer Survivable Branch Appliance oder auf einem Survivable Branch Server in Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)

