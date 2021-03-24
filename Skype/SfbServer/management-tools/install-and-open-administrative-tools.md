---
title: Installieren und Öffnen von Verwaltungstools
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: In diesem Thema wird beschrieben, wie Sie die verwaltungstechnischen Tools installieren und öffnen, die Sie zum Bereitstellen und Verwalten von Skype for Business benötigen.
ms.openlocfilehash: 72966026e414b3b36cfc49ab61bf41f045e1f864
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098781"
---
# <a name="install-and-open-administrative-tools"></a>Installieren und Öffnen von Verwaltungstools

In diesem Thema wird beschrieben, wie Sie die verwaltungstechnischen Tools installieren, die Sie zum Bereitstellen und Verwalten von Skype for Business Server benötigen. Die Verwaltungstools werden standardmäßig auf jedem Server installiert, auf dem Skype for Business Server ausgeführt wird. Sie können die Verwaltungstools auch auf anderen Computern wie etwa dedizierten Verwaltungskonsolen installieren. Es wird dringend empfohlen, die Verwaltungstools auf einem Computer zu installieren, der sich in derselben Domäne oder Gesamtstruktur wie die skype for Business Server-Bereitstellung befindet, die Sie erstellen, um sicherzustellen, dass die Vorbereitungsschritte für Active Directory-Domänendienste bereits abgeschlossen sind, wodurch Sie die Verwaltungstools auf diesem Computer später verwenden können, um Ihre Topologie zu veröffentlichen. Überprüfen Sie außerdem die erforderlichen Anforderungen, bevor Sie die Skype for Business Server-Verwaltungstools installieren oder verwenden. Weitere Informationen finden Sie in der Anforderungsdokumentation in [Skype for Business Server 2019](../../SfBServer2019/plan/system-requirements.md) oder Skype for Business Server [2015](../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md).
 
> [!Important]
> Wenn Ihre Organisation erfordert, dass Sie Internetinformationsdienste (Internet Information Services, IIS) und alle Webdienste auf einem anderen Laufwerk als dem Systemlaufwerk suchen, können Sie den Installationspfad für die Skype for Business Server-Dateien im Dialogfeld Setup ändern. Wenn Sie die Setupdateien zu diesem Pfad installieren, einschließlich OCSCore.msi, werden auch die restlichen Skype for Business Server-Dateien auf diesem Laufwerk bereitgestellt. 

## <a name="to-install-the-administrative-tools"></a>So installieren Sie die Verwaltungstools

1. Melden Sie sich mindestens als lokaler Administrator auf dem Computer an, auf dem der fea-cs-topo-tool und die Verwaltungstools installiert werden sollen. Wenn Sie als Standardbenutzer in der Windows- und Benutzerkontensteuerung (User Account Control, UAC) angemeldet sind, werden Sie aufgefordert, den lokalen Administrator oder einen domänenäquivalenten Benutzernamen und Kennwort einzugeben.
2. Suchen Sie auf Ihrem Computer nach dem Datenträger für die Installation, und doppelklicken Sie auf dem Computer auf \Setup\amd64\Setup.exe .
3. Wenn Sie aufgefordert werden, das verteilbare Microsoft Visual C++ zu installieren, klicken Sie auf **Ja**.
4. Klicken Sie auf der Seite Installationsspeicherort auf **OK**. Ändern Sie diesen Pfad in einen anderen Speicherort oder ein anderes Laufwerk, wenn Sie die Dateien an einem anderen Speicherort installieren müssen.

    > [!Important]
    > Wenn Ihre Organisation erfordert, dass Sie Internetinformationsdienste (Internet Information Services, IIS) und alle Webdienste auf einem anderen Laufwerk als dem Systemlaufwerk suchen, können Sie den Installationspfad für die Skype for Business Server-Dateien im Dialogfeld Setup ändern. Wenn Sie die Setupdateien zu diesem Pfad installieren, einschließlich OCSCore.msi, werden auch die restlichen Skype for Business Server-Dateien auf diesem Laufwerk bereitgestellt. 

5. Lesen Sie die Lizenzbedingungen auf der Seite Endbenutzer-Lizenzvertrag, klicken Sie auf **Ich stimme zu** und anschließend auf **OK**. Dieser Schritt ist erforderlich, um fortfahren zu können.
6. Klicken Sie auf der Seite Bereitstellungs-Assistent auf **Administratortools installieren.** 
7. Klicken Sie nach dem erfolgreichen Abschluss der Installation auf **Beenden**.

Verwenden Sie die folgenden Verfahren, um Verwaltungstools zum Bereitstellen, Konfigurieren oder Beheben von Problemen mit Ihrer Skype for Business Server-Topologie zu öffnen.

- [Bereitstellungs-Assistent](#deployment-wizard)
- [Topologie-Generator](#topology-builder) 
- [Skype for Business Server-Systemsteuerung](#skype-for-business-server-control-panel)
- [Skype for Business Server-Verwaltungsshell](#skype-for-business-server-management-shell)

## <a name="deployment-wizard"></a>Bereitstellungs-Assistent

Verwenden Sie das folgende Verfahren, um den Bereitstellungs-Assistenten lokal zu starten, um Komponentendateien hinzuzufügen oder zu entfernen.

**So starten Sie den Skype for Business Server-Bereitstellungs-Assistenten**

1. Melden Sie sich bei dem Computer an, auf dem der Skype for Business Server-Bereitstellungs-Assistent als Mitglied der Gruppe "Domänen-Admins" und der Gruppe "RTCUniversalServerAdmins" installiert ist.
2. Klicken **Sie auf Start,** **klicken Sie auf Alle Programme,** klicken Sie auf **Skype for Business Server,** und klicken Sie dann auf **Skype for Business Server Deployment Wizard**.


## <a name="topology-builder"></a>Topologie-Generator 

Verwenden Sie das folgende Verfahren, um den Topologie-Generator zu öffnen, um die Server zu definieren, die Sie in Ihrer Skype for Business Server-Topologie bereitstellen möchten.

**So öffnen Sie den Skype for Business Server Topology Builder zum Entwerfen der Topologie**

1. Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.
    > [!NOTE]
    > Sie können eine Topologie mithilfe eines Kontos definieren, das Mitglied der lokalen Gruppe "Benutzer" ist. Zum Lesen, Veröffentlichen oder Aktivieren einer Topologie, die zum Installieren von Skype for Business Server auf einem Server erforderlich ist, müssen Sie jedoch ein Konto verwenden, das Mitglied der Gruppe "Domänen-Admins" und der Gruppe "RTCUniversalServerAdmins" ist und über Vollzugriffsberechtigungen verfügt (d. h. , lesen, schreiben und ändern) für die Dateifreigabe, die Sie für den Archivierungsdateispeicher verwenden möchten, damit der Topologie-Generator die erforderliche DACLs (Discretionary Access Control List) oder ein Konto mit entsprechenden Benutzerrechten konfigurieren kann.
 
2. Start Topology Builder: Klicken Sie **auf Start,** klicken Sie auf **Alle Programme,** **klicken Sie auf Skype for Business Server,** und klicken Sie dann auf **Skype for Business Server Topology Builder**.

## <a name="skype-for-business-server-control-panel"></a>Skype for Business Server-Systemsteuerung 

Verwenden Sie eines der folgenden Verfahren, um die Skype for Business Server-Systemsteuerung zu öffnen, um die Konfiguration von Servern, Benutzern, Clients und Geräten in Ihrer Umgebung zu verwalten.

> [!NOTE]
> Sie können ein Benutzerkonto verwenden, das der Rolle "CsAdministrator" zugewiesen ist, um alle Aufgaben in der Skype for Business Server-Systemsteuerung auszuführen. Sie können andere Rollen verwenden, um sich bei der Skype for Business Server-Systemsteuerung zu anmelden, um bestimmte Verwaltungsaufgaben auszuführen, abhängig von der aufgabe, die Sie ausführen müssen. Sie können z. B. CSArchivingAdministrator verwenden, um die Archivierung in der Skype for Business Server-Systemsteuerung zu verwalten. Weitere Informationen zu Rollen finden Sie unter [Planning for role-based access control](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control). Ausführliche Informationen zu den Rollen, die Sie zum Ausführen einer bestimmten Aufgabe verwenden können, finden Sie in der Dokumentation für die Aufgabe. 

**So öffnen Sie die Skype for Business Server-Systemsteuerung von einem beliebigen Computer in der Firewall Ihrer Organisation**

1. Melden Sie sich über ein Benutzerkonto, das der Rolle "CsAdministrator" oder einer anderen Rolle zugewiesen ist, die über die entsprechenden Benutzerrechte und Berechtigungen für die auszuführende Aufgabe verfügt, bei jedem Beliebigen Computer in Ihrer internen Bereitstellung mit einer Bildschirmauflösung von mindestens 1024 x 768 an.

    > [!IMPORTANT]
    > Wenn Sie einen einfachen einheitlichen Ressourcen-Locator (URL) für die Verwaltung konfiguriert haben, können Sie über einen Internetbrowser auf die Skype for Business Server-Systemsteuerung zugreifen, der auf jedem Computer innerhalb der Firewall Ihrer Organisation ausgeführt wird. Weitere Informationen zum Konfigurieren der einfachen VERWALTUNGS-URL finden Sie unter [Planning for simple URLs](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-simple-urls) und [Edit or configure simple URLs](/previous-versions/office/lync-server-2013/lync-server-2013-edit-or-configure-simple-urls). 

2. Öffnen Sie ein Browserfenster, und geben Sie die für Ihre Organisation konfigurierte Admin-URL ein.

**So öffnen Sie die Skype for Business Server-Systemsteuerung auf einem Computer mit Skype for Business Server**

1. Melden Sie sich über ein Benutzerkonto, das Mitglied der Rolle "CsAdministrator" oder eine andere Rolle ist, die über die entsprechenden Benutzerrechte und Berechtigungen für die auszuführende Aufgabe verfügt, bei einem Computer an, auf dem Sie Skype for Business Server installiert haben, oder zumindest die Skype for Business Server-Verwaltungstools. Zum Konfigurieren von Einstellungen muss der Computer mindestens eine Bildschirmauflösung von 1024 x 768 haben.
2. Skype for Business Server-Systemsteuerung starten: Klicken Sie auf **Start,** klicken Sie auf **Alle** Programme, zeigen Sie auf Verwaltungstools, zeigen Sie auf Skype for Business **Server,** und klicken Sie dann auf Skype for Business **Server-Systemsteuerung**.

## <a name="skype-for-business-server-management-shell"></a>Skype for Business Server-Verwaltungsshell 

Führen Sie das folgende Verfahren aus, um die Skype for Business Server-Verwaltungsshell zu öffnen, um Server, Benutzer, Clients und Geräte in Ihrer Umgebung mithilfe der Befehlszeile zu verwalten.

> [!NOTE]
> Sie können ein Benutzerkonto verwenden, das der Rolle "CsAdministrator" zugewiesen ist, um alle Aufgaben in der Skype for Business Server-Verwaltungsshell auszuführen. Sie können sich mit anderen Rollen anmelden, um bestimmte Verwaltungsaufgaben auszuführen, je nachdem, welche Aufgabe Sie ausführen müssen. Sie können z. B. CSArchivingAdministrator zum Ausführen von Cmdlets im Zusammenhang mit der Archivierungsverwaltung verwenden. Weitere Informationen zu Rollen finden Sie unter [Planning for role-based access control](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control). Ausführliche Informationen zu den Rollen, die Sie zum Ausführen eines bestimmten Cmdlets verwenden können, finden Sie in der Dokumentation zum Cmdlet.<br/><br/>Sie können auch bestimmte Cmdlets mithilfe eines Benutzerkontos in den Gruppen RTCUniversalServerAdmins, RTCUniversalUserAdmins oder RTCUniversalReadOnlyAdmins ausführen, abhängig vom Cmdlet. 

**So öffnen Sie die Skype for Business Server-Verwaltungsshell**

Wenn Sie ein Windows PowerShell und nicht die Skype for Business Server Management Shell öffnen, können Sie die Skype for Business Server-Cmdlets standardmäßig nicht ausführen. Wenn Sie die Skype for Business Server-Cmdlets innerhalb Windows PowerShell ausführen möchten, geben Sie folgendes an der Eingabeaufforderung Windows PowerShell ein:

`Import-Module Lync`

Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start,** klicken Sie auf **Alle Programme,** **klicken Sie auf Skype for Business Server,** und klicken Sie dann **auf Skype for Business Server Management Shell**.