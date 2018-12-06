---
title: 'Lync Server 2013: Komponenten und Topologien für Konferenzen'
TOCTitle: Komponenten und Topologien für Konferenzen
ms:assetid: eb83052a-3360-4ba1-a6a0-6ee419942809
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg399061(v=OCS.15)
ms:contentKeyID: 49295795
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Komponenten und Topologien für Konferenzen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-04_

Wenn Sie im Topologie-Generator Konferenzen auswählen, werden Konferenzen als Teil des Front-End-Servers oder des Standard Edition-Servers implementiert. Für Einwahlkonferenzen und PowerPoint-Freigabe sind zusätzliche Komponenten und Konfigurationsschritte erforderlich. In den folgenden Abschnitten werden die unterstützten Komponenten und Topologien für Webkonferenzen, A/V-Konferenzen und Einwahlkonferenzen beschrieben.

## Unterstützte Komponenten

Die einzigen Komponenten, die für Webkonferenzen und A/V-Konferenzen erforderlich sind, sind der Front-End-Server oder der Standard Edition-Server Ihrer Organisation. Eine Aufstellung der Hardware- und Softwareanforderungen für den Front-End-Server und den Standard Edition-Server finden Sie unter [Unterstützte Hardware für Lync Server 2013](lync-server-2013-supported-hardware.md) und [Serversoftware- und Infrastrukturunterstützung in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).

In Lync Server 2013 werden Office Web Apps und der Office Web Apps-Server zur Verarbeitung der Freigabe und des Renderings von PowerPoint-Präsentationen verwendet. Weitere Informationen zum Installieren und Konfigurieren des Office Web Apps-Servers finden Sie unter [Konfigurieren der Integration mit Office Web Apps Server und Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

Für Einwahlkonferenzen werden zusätzlich zu den Anforderungen, die auch für Web- und A/V-Konferenzen gelten, die folgenden Lync Server 2013-Komponenten verwendet:

  - **Anwendungsdienst**   Der Anwendungsdienst bietet eine Plattform zum Bereitstellen, Hosten und Verwalten von Unified Communications-Anwendungen (UC). Bei Einwahlkonferenzen werden zwei UC-Anwendungen verwendet, die den Anwendungsdienst benötigen: Die Konferenzzentrale und die Konferenzankündigungsanwendung. Der Anwendungsdienst wird standardmäßig auf jedem Front-End-Server in einem Front-End-Pool und auf jedem Standard Edition-Server installiert und aktiviert, wenn Sie eine Konferenzarbeitsauslastung bereitstellen und die Option für Einwahlkonferenzen auswählen.

  - **Konferenzzentrale**   Die Konferenzzentrale ist eine Unified Communications-Anwendung, die Festnetzanrufe annimmt, Ansagen wiedergibt und Anrufe mit einer A/V-Konferenz verbindet. Die Konferenzzentrale wird standardmäßig installiert und aktiviert, wenn Sie eine Konferenzarbeitsauslastung bereitstellen und die Option für Einwahlkonferenzen auswählen.

  - **Konferenzankündigungsanwendung**   Die Konferenzankündigungsanwendung ist eine Unified Communications-Anwendung zur Wiedergabe von Signaltönen und Ansagen für Festnetzteilnehmer bei bestimmten Aktionen (z. B. wenn Teilnehmer einer Konferenz beitreten oder diese verlassen, wenn Teilnehmer stumm geschaltet werden oder die Stummschaltung aufgehoben wird, wenn Benutzer in der Lobby platziert werden oder wenn die Konferenz gesperrt bzw. entsperrt wird). Die Konferenzankündigungsanwendung unterstützt zudem DTMF-Befehle (Dual-Tone Multifrequency, Tonwahlverfahren) über die Telefontastatur. Die Konferenzankündigungsanwendung wird standardmäßig automatisch installiert und aktiviert, wenn Sie eine Konferenzarbeitsauslastung bereitstellen und die Option für Einwahlkonferenzen auswählen.

  - **Seite "Einstellungen für Einwahlkonferenz"**   Auf der Seite "Einstellungen für Einwahlkonferenz" werden die Konferenzeinwahlnummern mit den verfügbaren Sprachen, zugewiesene Konferenzinformationen (d. h. für Besprechungen, die nicht geplant werden müssen) und die in einer Konferenz verfügbaren DTMF-Steuerelemente angezeigt. Darüber hinaus können Benutzer auf dieser Seite ihre persönliche Identifikationsnummer (PIN) sowie zugewiesene Konferenzinformationen verwalten. Die Seite "Einstellungen für Einwahlkonferenz" wird automatisch als Teil der Webdienste installiert.

  - **Lync Server 2013- Vermittlungsserver und PSTN-Gateway**   Für Einwahlkonferenzen muss ein Vermittlungsserver Signaldatenverkehr (und in manchen Konfigurationen Mediendatenverkehr) zwischen Lync Server 2013 und dem PSTN-Gateway übersetzen, und ein PSTN-Gateway muss Signal- und Mediendatenverkehr zwischen dem Vermittlungsserver und dem Festnetz übersetzen. Für Einwahlkonferenzen müssen Sie mindestens einen Vermittlungsserver und mindestens eine der folgenden Komponenten bereitstellen:
    
      - PSTN-Gateway
    
      - IP-PBX
    
      - Session Border Controller (SBC) (für einen Anbieter von Internettelefoniediensten, mit dem durch Konfigurieren eines SIP-Trunks eine Verbindung hergestellt wird)
    

    > [!NOTE]
    > Wenn Sie außerdem Enterprise-VoIP, sind Vermittlungsserver und PSTN-Gateways Teil der Enterprise-VoIP-Bereitstellung. Wenn Sie keine Enterprise-VoIP-Funktionen bereitstellen, müssen Sie mindestens einen Vermittlungsserver und mindestens ein PSTN-Gateway, eine IP-Nebenstellenanlage oder einen SBC für Einwahlkonferenzen bereitstellen.



  - **Dateispeicher**   Der Dateispeicher wird für Audiodateien mit aufgezeichneten Namen verwendet. Er ist eine Standardkomponente in jeder Enterprise Edition- oder Standard Edition-Bereitstellung.

  - **Benutzerspeicher**   Der Benutzerspeicher wird zum Speichern von Lync Server 2013-Benutzer-PINs verwendet. Für PINs wird ein Hashalgorithmus verwendet. Der Benutzerspeicher ist eine Standardkomponente in jeder Enterprise Edition- oder Standard Edition-Bereitstellung.

  - **Lync Server-Systemsteuerung**   Bestimmte Einwahleinstellungen können mithilfe der Lync Server-Systemsteuerung konfiguriert werden.

  - **Lync Server-Verwaltungsshell**   Alle Einwahleinstellungen können mithilfe von Lync Server-Verwaltungsshell-Cmdlets konfiguriert werden. Es sind Lync Server-Verwaltungsshell-Cmdlets für die Bereitstellung, Konfiguration, Ausführung, Überwachung und Problembehandlung bei der Konferenzzentrale und der Konferenzankündigungsanwendung verfügbar. Ausführliche Informationen zu bestimmten Cmdlets finden Sie in der Dokumentation zur Lync Server-Verwaltungsshell.

## Unterstützte Topologien

In Lync Server 2013 wird der Server, auf dem die Konferenzdienste ausgeführt werden, immer gemeinsam mit dem Front-End-Server oder den Standard Edition-Servern ausgeführt. Während der ersten Bereitstellung erhalten Sie im Topologie-Generator die Option, Konferenzfunktionen in die Topologie einzubeziehen. Sie können mithilfe des Topologie-Generators auch einer vorhandenen Bereitstellung Konferenzen hinzufügen. Ausführliche Informationen finden Sie unter [Definieren und Konfigurieren der Topologie in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).

## Topologien für Einwahlkonferenzen

Sie können Einwahlkonferenzen in folgenden Topologien und Konfigurationen bereitstellen:

  - Lync Server 2013Standard Edition

  - Lync Server 2013Enterprise Edition

  - Mit oder ohne Enterprise-VoIP

Sie können den Anwendungsdienst, die Konferenzzentrale und die Konferenzankündigungsanwendung an einem zentralen Standort bereitstellen, aber nicht an einem Zweigstellenstandort.


> [!NOTE]
> Wenn Sie Einwahlkonferenzen bereitstellen, müssen Sie diese Funktion in jedem Pool bereitstellen, in dem Lync Server 2013-Konferenzen bereitgestellt werden. Sie müssen nicht in jedem Pool Zugriffsnummern zuweisen, aber Sie müssen die Funktion für Einwahlkonferenzen in jedem Pool bereitstellen. Diese Anforderung muss für die Funktion für aufgezeichnete Namen erfüllt werden, wenn ein Benutzer eine Zugriffsnummer aus einem Pool wählt, um an einer Lync Server 2013-Konferenz in einem anderen Pool teilzunehmen.



## Unterstützte Topologien für Lync Server 2013 und Office Web Apps

Lync Server 2013 bietet folgende Möglichkeiten zum Konfigurieren des Office Web Apps-Servers je nach Ihren Anforderungen:

  - **Installieren sowohl von Lync Server 2013 als auch des Office Web Apps-Servers lokal hinter der Firewall Ihrer Organisation und in derselben Netzwerkzone.** Mit dieser Topologie wird externer Zugriff auf den Office Web Apps-Server über den Reverseproxyserver bereitgestellt. Sowohl Lync Server 2013 als auch der Office Web Apps-Server (oder eine Office Web Apps-Server-Farm) werden lokal und hinter der Firewall Ihrer Organisation installiert. Idealerweise sollten Sie den Office Web Apps-Server in derselben Netzwerkzone installieren wie Lync Server.
    
    Externe Lync-Clients können eine Verbindung mit Lync Server 2013 und dem Office Web Apps-Server herstellen, indem sie einen Reverseproxyserver verwenden. Dies ist ein Server, der Anforderungen aus dem Internet empfängt und an das interne Netzwerk weiterleitet. (Interne Clients müssen den Reverseproxyserver nicht verwenden, weil sie keine direkte Verbindung mit dem Office Web Apps-Server herstellen können.) Diese Topologie eignet sich am besten, wenn Sie eine dedizierte Office Web Apps-Server-Farm verwenden möchten, die nur von Lync Server 2013 genutzt wird.

  - **Verwenden eines extern bereitgestellten Office Web Apps-Servers**
    
    In dieser Topologie wird Lync Server 2013 lokal bereitgestellt und verwendet einen Office Web Apps-Server, der außerhalb der Lync Server-Netzwerkzone bereitgestellt ist. Dies kann der Fall sein, wenn der Office Web Apps-Server von mehreren Anwendungen im Unternehmen gemeinsam verwendet wird und in einem Netzwerk bereitgestellt ist, in dem Lync Server die externe Schnittstelle des Office Web Apps-Servers verwenden muss, und umgekehrt.
    
    Sie müssen keinen Reverseproxyserver installieren. Vielmehr werden alle Anforderungen vom Office Web Apps-Server an Lync Server 2013 über den Edgeserver weitergeleitet. Sowohl die internen als auch die externen Lync-Clients stellen mithilfe der externen URL eine Verbindung mit dem Office Web Apps-Server her.
    
    Wird der Office Web Apps-Server außerhalb der internen Firewall bereitgestellt, dann wählen Sie im Topologie-Generator die Option **Office Web Apps Server wird in einem externen Netzwerk (d. h. Umkreis/Internet) bereitgestellt** aus. Weitere Informationen finden Sie unter [Konfigurieren der Integration mit Office Web Apps Server und Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

Unabhängig von der ausgewählten Topologie ist es entscheidend, dass die korrekten Firewallports geöffnet sind. Sie müssen sicherstellen, dass DNS-Namen, IP-Adressen und Ports nicht durch Firewalls auf dem Office Web Apps-Server, das Lastenausgleichssystem oder Lync Server blockiert werden.


> [!NOTE]
> Eine weitere Option zum Bereitstellen von externem Zugriff auf den Office Web Apps-Server besteht darin, den Server im Umkreisnetzwerk bereitzustellen. Wenn Sie sich dafür entscheiden, denken Sie daran, dass für das Setup des Office Web Apps-Servers der Servercomputer ein Mitglied der Active Directory-Domäne sein muss. Es wird davon abgeraten, den Office Web Apps-Server im Umkreisnetzwerk zu installieren, es sei denn, Ihre Netzwerkrichtlinie lässt zu, dass Computer im Umkreisnetzwerk Active Directory-Domänenmitglieder sind. Stattdessen sollten Sie den Office Web Apps-Server im internen Netzwerk installieren und externen Benutzern Zugriff über Ihren Reverseproxyserver ermöglichen.


