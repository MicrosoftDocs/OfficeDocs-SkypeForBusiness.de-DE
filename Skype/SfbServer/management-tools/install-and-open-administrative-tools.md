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
description: In diesem Thema wird beschrieben, wie Sie die Verwaltungstools installieren und öffnen, die Sie zum Bereitstellen und Verwalten von Skype for Business benötigen.
ms.openlocfilehash: d31fe784b62a5d709049dc5061e323034065df37
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835095"
---
# <a name="install-and-open-administrative-tools"></a>Installieren und Öffnen von Verwaltungstools

In diesem Thema wird beschrieben, wie Sie die Verwaltungstools installieren, die Sie zum Bereitstellen und Verwalten von Skype for Business Server benötigen. Die Verwaltungstools werden standardmäßig auf jedem Server mit Skype for Business Server installiert. Sie können die Verwaltungstools auch auf anderen Computern wie etwa dedizierten Verwaltungskonsolen installieren. Es wird dringend empfohlen, die Verwaltungstools auf einem Computer zu installieren, der sich in derselben Domäne oder Gesamtstruktur wie die skype for Business Server-Bereitstellung befindet, die Sie erstellen, um sicherzustellen, dass die Vorbereitungsschritte für active Directory Domain Services bereits abgeschlossen sind, wodurch Sie die Verwaltungstools auf diesem Computer später zum Veröffentlichen Ihrer Topologie verwenden können. Überprüfen Sie außerdem die erforderlichen Anforderungen, bevor Sie die Skype for Business Server-Verwaltungstools installieren oder verwenden. Weitere Informationen finden Sie in der Dokumentation zu den Anforderungen in [Skype for Business Server 2019](../../SfBServer2019/plan/system-requirements.md) oder Skype for Business Server [2015.](../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md)
 
> [!Important]
> Wenn In Ihrer Organisation Internetinformationsdienste (Internet Information Services, IIS) und alle Webdienste auf einem anderen Laufwerk als dem Systemlaufwerk suchen müssen, können Sie den Installationspfad für die Skype for Business Server-Dateien im Dialogfeld "Setup" ändern. Wenn Sie die Setupdateien unter diesem Pfad installieren, einschließlich OCSCore.msi, werden auch die restlichen Skype for Business Server-Dateien auf diesem Laufwerk bereitgestellt. 

## <a name="to-install-the-administrative-tools"></a>So installieren Sie die Verwaltungstools

1. Melden Sie sich mindestens als lokaler Administrator auf dem Computer an, auf dem der fea-cs-topo-tool und die Verwaltungstools installiert werden sollen. Wenn Sie als Standardbenutzer in Windows angemeldet sind und die Benutzerkontensteuerung (User Account Control, UAC) aktiviert ist, werden Sie aufgefordert, den lokalen Administrator oder einen domänenäquivalenten Benutzernamen und ein Kennwort einzugeben.
2. Suchen Sie auf Ihrem Computer nach dem Datenträger für die Installation, und doppelklicken Sie auf dem Computer auf \Setup\amd64\Setup.exe .
3. Wenn Sie aufgefordert werden, das verteilbare Microsoft Visual C++-Paket zu installieren, klicken Sie auf **"Ja".**
4. Klicken Sie auf der Seite "Installationsspeicherort" auf **"OK".** Ändern Sie diesen Pfad in einen anderen Speicherort oder ein anderes Laufwerk, wenn Sie die Dateien an einem anderen Speicherort installieren müssen.

    > [!Important]
    > Wenn In Ihrer Organisation Internetinformationsdienste (Internet Information Services, IIS) und alle Webdienste auf einem anderen Laufwerk als dem Systemlaufwerk suchen müssen, können Sie den Installationspfad für die Skype for Business Server-Dateien im Dialogfeld "Setup" ändern. Wenn Sie die Setupdateien unter diesem Pfad installieren, einschließlich OCSCore.msi, werden auch die restlichen Skype for Business Server-Dateien auf diesem Laufwerk bereitgestellt. 

5. Lesen Sie die Lizenzbedingungen auf der Seite Endbenutzer-Lizenzvertrag, klicken Sie auf **Ich stimme zu** und anschließend auf **OK**. Dieser Schritt ist erforderlich, um fortfahren zu können.
6. Klicken Sie auf der Seite "Bereitstellungs-Assistent" **auf "Administratortools installieren".** 
7. Klicken Sie nach dem erfolgreichen Abschluss der Installation auf **Beenden**.

Verwenden Sie die folgenden Verfahren, um Verwaltungstools zum Bereitstellen, Konfigurieren oder Beheben von Problemen mit Ihrer Skype for Business Server-Topologie zu öffnen.

- [Bereitstellungs-Assistent](#deployment-wizard)
- [Topologie-Generator](#topology-builder) 
- [Skype for Business Server-Systemsteuerung](#skype-for-business-server-control-panel)
- [Skype for Business Server-Verwaltungsshell](#skype-for-business-server-management-shell)

## <a name="deployment-wizard"></a>Bereitstellungs-Assistent

Verwenden Sie das folgende Verfahren, um den Bereitstellungsassistenten lokal zu starten, um Komponentendateien hinzuzufügen oder zu entfernen.

**So starten Sie den Skype for Business Server-Bereitstellungs-Assistenten**

1. Melden Sie sich an dem Computer an, auf dem der Skype for Business Server-Bereitstellungs-Assistent installiert ist, als Mitglied der Gruppe "Domänen-Admins" und der Gruppe "RTCUniversalServerAdmins".
2. Klicken **Sie auf "Start",** **"Alle Programme",** **"Skype for Business Server"** und dann auf **"Skype for Business Server-Bereitstellungs-Assistent".**


## <a name="topology-builder"></a>Topologie-Generator 

Verwenden Sie das folgende Verfahren, um den Topologie-Generator zu öffnen, um die Server zu definieren, die Sie in Ihrer Skype for Business Server-Topologie bereitstellen möchten.

**So öffnen Sie den Skype for Business Server-Topologie-Generator zum Entwerfen der Topologie**

1. Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.
    > [!NOTE]
    > Sie können eine Topologie definieren, indem Sie ein Konto verwenden, das Mitglied der lokalen Benutzergruppe ist. Zum Lesen, Veröffentlichen oder Aktivieren einer Topologie, die zum Installieren von Skype for Business Server auf einem Server erforderlich ist, müssen Sie jedoch ein Konto verwenden, das Mitglied der Gruppe "Domänen-Admins" und der Gruppe "RTCUniversalServerAdmins" ist und über Vollzugriff verfügt (d. h. , lesen, schreiben und ändern) für die Dateifreigabe, die Sie für den Archivierungsdateispeicher verwenden möchten, damit der Topologie-Generator die erforderliche DACLs (Discretionary Access Control List) oder ein Konto mit entsprechenden Benutzerrechten konfigurieren kann.
 
2. Starten Sie den Topologie-Generator: Klicken Sie **auf "Start",**"Alle Programme",  **"Skype for Business Server"** und dann auf **"Skype for Business Server-Topologie-Generator".**

## <a name="skype-for-business-server-control-panel"></a>Skype for Business Server-Systemsteuerung 

Verwenden Sie eines der folgenden Verfahren, um die Skype for Business Server-Systemsteuerung zu öffnen, um die Konfiguration von Servern, Benutzern, Clients und Geräten in Ihrer Umgebung zu verwalten.

> [!NOTE]
> Sie können ein Benutzerkonto verwenden, das der Rolle "CsAdministrator" zugewiesen ist, um alle Aufgaben in der Skype for Business Server-Systemsteuerung auszuführen. Sie können andere Rollen verwenden, um sich bei der Skype for Business Server-Systemsteuerung zu anmelden, um bestimmte Verwaltungsaufgaben auszuführen, abhängig von der aufgabe, die Sie ausführen müssen. Sie können z. B. "CSArchivingAdministrator" verwenden, um die Archivierung in der Skype for Business Server-Systemsteuerung zu verwalten. Weitere Informationen zu Rollen finden Sie unter ["Planen der rollenbasierten Zugriffssteuerung".](https://technet.microsoft.com/library/gg425917(v=ocs.15).aspx) Ausführliche Informationen zu den Rollen, die Sie zum Ausführen einer bestimmten Aufgabe verwenden können, finden Sie in der Dokumentation für die Aufgabe. 

**So öffnen Sie die Skype for Business Server-Systemsteuerung von einem beliebigen Computer innerhalb der Firewall Ihrer Organisation**

1. Melden Sie sich über ein Benutzerkonto, das der Rolle "CsAdministrator" oder einer anderen Rolle mit den entsprechenden Benutzerrechten und -berechtigungen für die auszuführende Aufgabe zugewiesen ist, bei einem beliebigen Computer in Ihrer internen Bereitstellung mit einer Bildschirmauflösung von mindestens 1024 x 768 an.

    > [!IMPORTANT]
    > Wenn Sie eine einfache URL (Uniform Resource Locator) für die Verwaltung konfiguriert haben, können Sie über einen Internetbrowser auf die Skype for Business Server-Systemsteuerung zugreifen, der auf einem beliebigen Computer innerhalb der Firewall Ihrer Organisation ausgeführt wird. Weitere Informationen zum Konfigurieren der einfachen URL für die Verwaltung finden Sie unter "Planen einfacher [URLs"](https://technet.microsoft.com/library/gg398287(v=ocs.15).aspx) und ["Bearbeiten oder Konfigurieren einfacher URLs".](https://technet.microsoft.com/library/gg398063(v=ocs.15).aspx) 

2. Öffnen Sie ein Browserfenster, und geben Sie die für Ihre Organisation konfigurierte Admin-URL ein.

**So öffnen Sie die Skype for Business Server-Systemsteuerung auf einem Computer mit Skype for Business Server**

1. Melden Sie sich mit einem Benutzerkonto, das Mitglied der Rolle "CsAdministrator" oder einer anderen Rolle ist, die über die entsprechenden Benutzerrechte und -berechtigungen für die auszuführende Aufgabe verfügt, an einem Computer an, auf dem Sie Skype for Business Server oder zumindest die Skype for Business Server-Verwaltungstools installiert haben. Zum Konfigurieren von Einstellungen muss der Computer mindestens eine Bildschirmauflösung von 1024 x 768 haben.
2. Starten Sie die Skype for Business Server-Systemsteuerung: Klicken Sie auf **"Start",** klicken Sie auf "Alle Programme", zeigen Sie auf **"Verwaltung",** zeigen Sie auf **Skype for Business Server,** und klicken Sie dann auf **"Skype for Business Server-Systemsteuerung".**

## <a name="skype-for-business-server-management-shell"></a>Skype for Business Server-Verwaltungsshell 

Verwenden Sie das folgende Verfahren, um die Skype for Business Server Management Shell zum Verwalten von Servern, Benutzern, Clients und Geräten in Ihrer Umgebung über die Befehlszeile zu öffnen.

> [!NOTE]
> Sie können ein Benutzerkonto verwenden, das der Rolle "CsAdministrator" zugewiesen ist, um alle Aufgaben in der Skype for Business Server-Verwaltungsshell auszuführen. Sie können sich abhängig von der aufgabe, die Sie ausführen müssen, mit anderen Rollen anmelden, um bestimmte Verwaltungsaufgaben auszuführen. Sie können z. B. CSArchivingAdministrator zum Ausführen von Cmdlets im Zusammenhang mit der Archivierungsverwaltung verwenden. Weitere Informationen zu Rollen finden Sie unter ["Planen der rollenbasierten Zugriffssteuerung".](https://technet.microsoft.com/library/gg425917(v=ocs.15).aspx) Ausführliche Informationen zu den Rollen, die Sie zum Ausführen eines bestimmten Cmdlets verwenden können, finden Sie in der Dokumentation für das Cmdlet.<br/><br/>Sie können auch bestimmte Cmdlets mithilfe eines Benutzerkontos in den Gruppen RTCUniversalServerAdmins, RTCUniversalUserAdmins oder RTCUniversalReadOnlyAdmins ausführen, abhängig vom Cmdlet. 

**So öffnen Sie die Skype for Business Server-Verwaltungsshell**

Wenn Sie ein Windows PowerShell und nicht die Skype for Business Server-Verwaltungsshell öffnen, können Sie standardmäßig die Skype for Business Server-Cmdlets nicht ausführen. Wenn Sie die Skype for Business Server-Cmdlets in Windows PowerShell ausführen möchten, geben Sie an der Windows PowerShell Eingabeaufforderung Folgendes ein:

`Import-Module Lync`

Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie **auf "Start",**"Alle **Programme",** **"Skype for Business Server"** und dann auf **"Skype for Business Server Management Shell".**
