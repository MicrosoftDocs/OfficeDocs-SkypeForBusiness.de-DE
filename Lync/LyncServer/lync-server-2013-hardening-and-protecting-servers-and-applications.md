---
title: 'Lync Server 2013: Sichern und Schützen von Servern und Anwendungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hardening and protecting servers and applications for Lync Server 2013
ms:assetid: 9ca2b233-26f1-4d72-96e7-81a82c727806
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518331(v=OCS.15)
ms:contentKeyID: 62625491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00fea9bd192dedaf16567209798f12c7bff23e6a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832090"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardening-and-protecting-servers-and-applications-for-lync-server-2013"></a>Sichern und Schützen von Servern und Anwendungen für Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-12-05_

Sie sollten Ihr Betriebssystem und ihre Anwendungen entsprechend den bewährten Methoden für diese bestimmte Komponente verhärten und schützen. In diesem Abschnitt wird beschrieben, wie Anwendungsserver gehärtet und Gruppenrichtlinien zum Implementieren von Sicherheits Sperrungen verwendet werden.

<div>


> [!NOTE]  
> Sie können auch die Datenbanken verhärten und schützen, die für die Bereitstellung von Microsoft lync Server 2013 verwendet werden. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-hardening-and-protecting-databases.md">Härten und schützen der Datenbanken von lync Server 2013</A>.



</div>

<div>

## <a name="securing-application-servers"></a>Sichern von Anwendungsservern

Bei Anwendungsservern sollten das Betriebssystem und die Anwendung gehärtet werden. Beispielsweise sollte ein Windows Server 2008-Computer, der für die Ausführung von Microsoft Internet Security and Acceleration (ISA) Server 2006 dediziert ist, aus dem Betriebssystem und aus der Anwendungsperspektive gehärtet werden. Das Minimieren der Anzahl der Dienste, die vom Server ausgeführt und bereitgestellt werden, sollte ein Hauptziel sein.

</div>

<div>

## <a name="securing-virtual-servers"></a>Sichern von virtuellen Servern

Snapshots virtueller Server enthalten Kopien der Datenlaufwerke des Servers und enthalten auch Speicherabbilder von Daten im Arbeitsspeicher, die beide vertrauliche kryptografische Daten enthalten können, die zu Angriffen führen können. Bei Produktionsservern, die mithilfe von Virtualisierung implementiert werden, sollten Sie alle Server-Snapshots deaktivieren oder auf sehr kontrollierte Weise verwalten. Details zum Sichern von virtuellen Hyper-v-Servern finden Sie im Hyper-v-Sicherheitshandbuch [http://go.microsoft.com/fwlink/p/?LinkId=214176](http://go.microsoft.com/fwlink/p/?linkid=214176)unter:.

</div>

<div>

## <a name="group-policy"></a>Gruppenrichtlinie

In Windows Server 2008 und Windows Server 2008 R2 bietet die Gruppenrichtlinie die verzeichnisbasierte Verwaltung der Desktopkonfiguration. Sie können Gruppenrichtlinien zum Implementieren von Sicherheits Sperrungen verwenden, indem Sie für die folgenden Computer-und Benutzereinstellungen in einem Gruppenrichtlinienobjekt definieren:

  - Registrierungsbasierte Richtlinien

  - Sicherheit

  - Software Installation

  - Skripts

  - Ordnerumleitung

  - Remoteinstallationsdienste

Zum Bereitstelleneiner Benutzeroberfläche für den Administrator zum Konfigurieren dieser Einstellungen werden administrative Vorlagen mit Betriebssystemversionen, Service Pack-Versionen und einigen Anwendungen, einschließlich lync Server 2013, ausgeliefert.

Die Datei "Communicator. adm" ist eine administrative Vorlage, die mit lync Server 2013 ausgeliefert wird, im Verzeichnis%\\windir\\ % inf installiert ist und eine Schnittstelle zu den Gruppenrichtlinieneinstellungen bereitstellt. Jede Einstellung in Communicator. adm entspricht einer Einstellung in der Registrierung, die sich auf das Anwendungsverhalten auswirkt.

Auf die Einstellungen kann von gpedit. dll aus zugegriffen werden, die über die Konsole Active Directory-Benutzer und-Computer und die Gruppenrichtlinien-Verwaltungskonsole (Group Policy Management Console, GPMC) zur Verfügung steht.

</div>

<div>

## <a name="group-policy-security-settings"></a>Sicherheitseinstellungen für Gruppenrichtlinien

Gruppenrichtlinien enthalten Sicherheitseinstellungen für ein GPO unter Computer Konfiguration/Windows-Einstellungen/Sicherheitseinstellungen, wenn von "gpedit. dll" aus zugegriffen wird. Sie können Sicherheitsvorlagen importieren, um Sicherheitseinstellungen für das Gruppenrichtlinienobjekt zu konfigurieren. Im Windows Server 2008-Sicherheitshandbuch [http://go.microsoft.com/fwlink/p/?LinkId=145186](http://go.microsoft.com/fwlink/p/?linkid=145186) und im Windows Server 2008 R2 Security Compliance Management Toolkit [http://go.microsoft.com/fwlink/p/?LinkId=211882](http://go.microsoft.com/fwlink/p/?linkid=211882) finden Sie eine Reihe von Beispielvorlagen, die Sie Ihren Anforderungen entsprechend ändern können.

</div>

<div>

## <a name="best-practices"></a>Bewährte Methoden

  - Härten Sie alle Server Betriebssysteme und-Anwendungen aus.

  - Schützen Sie Server-Snapshots, und verbessern Sie die Sicherheit aller virtuellen Server.

  - Verwenden Sie Gruppenrichtlinien, um Sicherheits Sperrungen zu implementieren.

</div>

</div>

<span> </span>

</div>

</div>

</div>

