---
title: Konfigurieren von Partneranwendungen in Microsoft Lync Server 2013 und Microsoft Exchange Server 2013
TOCTitle: Konfigurieren von Partneranwendungen in Microsoft Lync Server 2013 und Microsoft Exchange Server 2013
ms:assetid: 9c3a3054-6201-433f-b128-4c49d3341370
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688151(v=OCS.15)
ms:contentKeyID: 49890859
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Partneranwendungen in Microsoft Lync Server 2013 und Microsoft Exchange Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

An einer Authentifizierung zwischen Servern sind üblicherweise drei Entitäten beteiligt: Die beiden Server, die miteinander kommunizieren müssen, und ein Sicherheitstokenserver eines Drittanbieters. Wenn zwei Server (z. B. Server A und Server B) miteinander kommunizieren müssen, beginnen beide Server in der Regel damit, dass sie einen Tokenserver kontaktieren und ein gegenseitig als vertrauenswürdig eingestuftes Sicherheitstoken erhalten. Server A präsentiert das Sicherheitstoken dann Server B (und umgekehrt), womit beide ihre Authentizität und Vertrauenswürdigkeit nachweisen.

Dies ist jedoch eine allgemeine Regel. Lync Server 2013, Microsoft Exchange Server 2013 und Microsoft SharePoint Server 2013 benötigen keinen Tokenserver eines Drittanbieters, wenn beide miteinander kommunizieren. Diese Serverprodukte können Sicherheitstoken erstellen, die gegenseitig akzeptiert werden. Daher ist kein separater Tokenserver erforderlich. (Diese Möglichkeit ist nur in Lync Server 2013, Exchange 2013 und SharePoint Server 2013 verfügbar. Falls Sie eine Authentifizierung zwischen Servern mit anderen Server einrichten müssen (auch mit anderen Microsoft-Serverprodukten), müssen Sie hierzu einen Tokenserver eines Drittanbieters einsetzen.)

Um eine Authentifizierung zwischen Lync Server und Exchange einzurichten, sind zwei Schritte erforderlich: 1) Sie müssen jedem Server das passende Zertifikat zuweisen und 2) Sie müssen beide Server als Partneranwendung des anderen Servers konfigurieren: Dies bedeutet, dass Sie Lync Server 2013 als Partneranwendung für Exchange 2013 und Exchange 2013 als Partneranwendung für Lync Server 2013 konfigurieren müssen.

## Konfigurieren von Lync Server 2013 als Partneranwendung für Exchange 2013

Das einfachste Verfahren, um mit Exchange 2013Lync Server 2013 als Partneranwendung zu konfigurieren, besteht darin, das Skript "Configure-EnterprisePartnerApplication.ps1" auszuführen. Dies ist ein Windows PowerShell-Skript, das mit Exchange 2013 geliefert wird. Um das Skript auszuführen, muss die URL für das Lync Server-Authentifizierungsmetadatendokument angegeben werden. Dies ist in der Regel der vollqualifizierte Domänenname des SharePoint-Pools, gefolgt vom Suffix "/metadata/json/1". Beispiel:

    https://atl-cs-001.litwareinc.com/metadata/json/1

Öffnen Sie für die Konfiguration von Lync Server als Partneranwendung die Exchange-Verwaltungsshell und führen Sie einen Befehl wie diesen aus (in der Annahme, dass Exchange auf Laufwerk "C:" installiert ist und das der Standardordnerpfad verwendet wird):

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"

Nach der Konfiguration der Partneranwendung empfiehlt es sich, Internet Information Services (IIS) auf Ihren Exchange-Postfach- und -Clientzugriffsservern zu beenden und neu zu starten. Sie können IIS mit einem Befehl wie dem folgenden neu starten. Dieser startet den Dienst auf dem Computer "atl-exchange-001":

    iisreset atl-exchange-001

Dieser Befehl kann in der Exchange-Verwaltungsshell oder in einem anderen Befehlfenster ausgeführt werden, das mit Administratorberechtigungen ausgeführt wird.

## Konfigurieren von Exchange 2013 als Partneranwendung für Lync Server 2013

Nachdem Sie Lync Server 2013 als Partneranwendung für Exchange 2013 konfiguriert haben, müssen Sie Exchange als Partneranwendung für Lync Server konfigurieren. Dies können Sie mit der Lync Server-Verwaltungsshell durchführen und indem Sie das Authentifizierungsmetadatendokument für Exchange angeben. Dies ist in der Regel der URI des Exchange-AutoErmittlungsdiensts gefolgt vom Suffix "/metadata/json/1". Beispiel:

    https://autodiscover.litwareinc.com/autodiscover/metadata/json/1

In Lync Server werden Partneranwendungen mit dem [New-CsPartnerApplication](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsPartnerApplication)-Cmdlet konfiguriert. Neben der Angabe des Metadaten-URI sollte für die Vertrauensstufe der Anwendung das volle Vertrauen festgelegt werden. Dadurch kann Exchange sowohl sich selbst als auch jeden autorisierten Benutzer im Bereich repräsentieren. Beispiel:

    New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"

Alternativ können Sie eine Partneranwendung erstellen, indem Sie den Skriptcode in der Lync Server 2013-Dokumentation zur Authentifizierung zwischen Servern kopieren und anpassen. Weitere Informationen finden Sie im Artikel [Verwalten von Server-zu-Server-Authentifizierung (OAuth) und Partneranwendungen](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md).

Wenn Sie die Partneranwendungen für Lync Server und Exchange erfolgreich konfiguriert haben, bedeutet dies, dass Sie die Authentifizierung zwischen Servern für die beiden Produkte konfiguriert haben. Lync Server 2013 enthält ein Windows PowerShell-Cmdlet, [Test-CsExStorageConnectivity](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsExStorageConnectivity), mit dem Sie überprüfen können, ob die Authentifizierung zwischen Servern richtig konfiguriert ist und ob der Lync Server-Speicherdienst eine Verbindung zu Exchange 2013 herstellen kann. Das Cmdlet stellt hierzu eine Verbindung zum Postfach eines Exchange 2013-Benutzers her, schreibt ein Element in den Ordner mit dem Unterhaltungsverlauf des Benutzers und löscht das Element optional im Anschluss.

Führen Sie zum Testen der Integration von Lync Server 2013 und Exchange 2013 in der Lync Server-Verwaltungsshell einen Befehl wie diesen aus:

    Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"

Im vorherigen Befehl steht die SipUri für die SIP-Adresse eines Benutzers mit einem Konto bei Exchange 2013. Der Befehl schlägt fehl, wenn es sich dabei nicht um ein gültiges Benutzerkonto handelt.

Wenn der Test erfolgreich war und die Verbindung hergestellt ist, können Sie mit der Konfiguration optionaler Funktionen, wie der Integration der Archivierung und dem einheitlichen Kontaktspeicher fortfahren.

