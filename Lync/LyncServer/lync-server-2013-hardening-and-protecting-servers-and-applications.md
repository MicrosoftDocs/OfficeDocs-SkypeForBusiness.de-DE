---
title: 'Lync Server 2013: Härten und schützen von Servern und Anwendungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardening and protecting servers and applications for Lync Server 2013
ms:assetid: 9ca2b233-26f1-4d72-96e7-81a82c727806
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518331(v=OCS.15)
ms:contentKeyID: 62625491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3533bcf01338a056bab8c75d1409530fab7c901f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536882"
---
# <a name="hardening-and-protecting-servers-and-applications-for-lync-server-2013"></a>Härten und schützen von Servern und Anwendungen für lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-12-05_

Sie sollten Ihr Betriebssystem und Ihre Anwendungen gemäß den bewährten Methoden für die jeweilige Komponente sichern und schützen. In diesem Abschnitt wird beschrieben, wie Sie Anwendungsserver sichern und schützen und mithilfe von Gruppenrichtlinien Sicherheitssperren implementieren.

<div>


> [!NOTE]  
> Sie können auch die für Sie Microsoft lync Server 2013 Bereitstellung verwendeten Datenbanken verhärten und schützen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-hardening-and-protecting-databases.md">Hardening and Protecting the databases of lync Server 2013</A>.



</div>

<div>

## <a name="securing-application-servers"></a>Sichern von Anwendungsservern

Bei Anwendungsservern sollten das Betriebssystem und die Anwendungen gesichert werden. Beispielsweise sollte ein Windows Server 2008-Computer für den Betrieb von Microsoft Internet Security and Acceleration (ISA) Server 2006 auf Betriebssystemebene und auf Anwendungsebene gesichert werden. Dabei sollte die Minimierung der Zahl der Dienste, die vom Server ausgeführt und bereitgestellt werden, ein vorrangiges Ziel sein.

</div>

<div>

## <a name="securing-virtual-servers"></a>Sichern von virtuellen Servern

Snapshots virtueller Server enthalten Kopien der Datenträger des Servers und enthalten auch Dumps von Daten im Arbeitsspeicher, die beide vertrauliche kryptografische Daten enthalten können, die zu Angriffen führen könnten. Bei Produktionsservern, die mithilfe von Virtualisierung implementiert werden, sollten Sie alle Server-Snapshots deaktivieren oder diese auf sehr kontrollierte Weise verwalten. Ausführliche Informationen zum Sichern virtueller Hyper-v-Server finden Sie im Hyper-v-Sicherheitshandbuch unter: [https://go.microsoft.com/fwlink/p/?LinkId=214176](https://go.microsoft.com/fwlink/p/?linkid=214176) .

</div>

<div>

## <a name="group-policy"></a>Gruppenrichtlinien

In Windows Server 2008 und Windows Server 2008 R2 ermöglichen Gruppenrichtlinien eine verzeichnisbasierte Desktopkonfigurationsverwaltung. Mithilfe von Gruppenrichtlinien können Sie Sicherheitssperren implementieren, indem Sie Computer- und Benutzereinstellungen innerhalb eines Gruppenrichtlinienobjekts (GPO) für folgende Bereiche definieren:

  - Registrierungsbasierte Richtlinien

  - Sicherheit

  - Softwareinstallation

  - Skripts

  - Ordnerumleitung

  - Remoteinstallationsdienste

Um eine Benutzeroberfläche für den Administrator zum Konfigurieren dieser Einstellungen bereitzustellen, werden administrative Vorlagen mit Betriebssystemversionen, Service Pack-Versionen und einigen Anwendungen einschließlich lync Server 2013 ausgeliefert.

Die Datei "Communicator. adm" ist eine administrative Vorlage, die mit lync Server 2013 ausgeliefert wird, im Verzeichnis% windir% inf installiert ist \\ \\ und eine Schnittstelle zu den Gruppenrichtlinieneinstellungen bereitstellt. Jede Einstellung in Communicator. adm entspricht einer Einstellung in der Registrierung, die sich auf das Anwendungsverhalten auswirkt.

Sie können über die Datei GPedit.dll auf die Einstellungen zugreifen. Diese Datei können Sie über die Konsole Active Directory-Benutzer und -Computer und über die Gruppenrichtlinien-Verwaltungskonsole aufrufen.

</div>

<div>

## <a name="group-policy-security-settings"></a>Sicherheitseinstellungen in Gruppenrichtlinien

Die Gruppenrichtlinie enthält Sicherheitseinstellungen für ein GPO unter Computer Konfiguration/Windows-Einstellungen/Sicherheitseinstellungen, wenn auf GPedit.dll zugegriffen wird. Sie können Sicherheitsvorlagen importieren, um Sicherheitseinstellungen für das GPO zu konfigurieren. Das Windows Server 2008 Security Guide [https://go.microsoft.com/fwlink/p/?LinkId=145186](https://go.microsoft.com/fwlink/p/?linkid=145186) and the Windows Server 2008 R2 Security Compliance Management Toolkit unter [https://go.microsoft.com/fwlink/p/?LinkId=211882](https://go.microsoft.com/fwlink/p/?linkid=211882) enthält eine Reihe von Beispielvorlagen, die Sie Ihren Anforderungen entsprechend ändern können.

</div>

<div>

## <a name="best-practices"></a>Bewährte Methoden

  - Sichern Sie alle Serverbetriebssysteme und -anwendungen.

  - Schützen Sie Servermomentaufnahmen, und erhöhen Sie die Sicherheit aller virtuellen Server.

  - Implementieren Sie Sicherheitssperren mithilfe von Gruppenrichtlinien.

</div>

</div>

<span> </span>

</div>

</div>

</div>

