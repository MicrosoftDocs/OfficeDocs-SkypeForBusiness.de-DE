---
title: Installieren und Öffnen von Verwaltungstools
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: In diesem Thema wird beschrieben, wie Sie die Verwaltungstools installieren und öffnen, die Sie zum Bereitstellen und Verwalten von Skype for Business benötigen.
ms.openlocfilehash: b2d06d14263174229d35ff2e5108574296bb5034
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031069"
---
# <a name="install-and-open-administrative-tools"></a>Installieren und Öffnen von Verwaltungstools

In diesem Thema wird beschrieben, wie Sie die Verwaltungstools installieren, die Sie zum Bereitstellen und Verwalten von Skype for Business Server benötigen. Die Verwaltungstools werden auf jedem Server mit Skype for Business Server standardmäßig installiert. Sie können die Verwaltungstools auch auf anderen Computern wie etwa dedizierten Verwaltungskonsolen installieren. Es wird dringend empfohlen, dass Sie die Verwaltungstools auf einem Computer installieren, der sich in der gleichen Domäne oder Gesamtstruktur wie die Skype for Business Server Bereitstellung befindet, die Sie erstellen, um sicherzustellen, dass Active Directory-Domänendienste Vorbereitungsschritte bereits abgeschlossen sind. Damit können Sie die Verwaltungstools auf diesem Computer später zum Veröffentlichen Ihrer Topologie verwenden. Stellen Sie außerdem sicher, dass Sie die erforderlichen Anforderungen überprüfen, bevor Sie die Skype for Business Server Verwaltungstools installieren oder verwenden. Weitere Informationen finden Sie in der Dokumentation zu den Anforderungen [Skype for Business Server 2019](../../SfBServer2019/plan/system-requirements.md) oder [Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md).
 
> [!Important]
> Wenn in Ihrer Organisation Internet Information Services (IIS) und alle Webdienste auf einem anderen Laufwerk als dem Systemlaufwerk gefunden werden müssen, können Sie den Pfad für den Installationspfad für die Skype for Business Server Dateien im Dialogfeld Setup ändern. Wenn Sie die Setup Dateien in diesem Pfad installieren, einschließlich OCSCore. msi, werden auch die restlichen Skype for Business Server Dateien auf diesem Laufwerk bereitgestellt. 

## <a name="to-install-the-administrative-tools"></a>So installieren Sie die Verwaltungstools

1. Melden Sie sich mindestens als lokaler Administrator auf dem Computer an, auf dem der fea-cs-topo-tool und die Verwaltungstools installiert werden sollen. Wenn Sie als Standardbenutzer in Windows angemeldet sind und die Benutzerkontensteuerung (User Account Control, UAC) aktiviert ist, werden Sie aufgefordert, den lokalen Administrator oder einen Domänen äquivalenten Benutzernamen und ein Kennwort einzugeben.
2. Suchen Sie auf Ihrem Computer nach dem Datenträger für die Installation, und doppelklicken Sie auf dem Computer auf \Setup\amd64\Setup.exe .
3. Wenn Sie zur Installation von Microsoft Visual C++ Distributed aufgefordert werden, klicken Sie auf **Ja**.
4. Klicken Sie auf der Seite Installationsspeicherort auf **OK**. Ändern Sie diesen Pfad in einen anderen Speicherort oder ein anderes Laufwerk, wenn Sie die Dateien an einem anderen Speicherort installieren müssen.

    > [!Important]
    > Wenn in Ihrer Organisation Internet Information Services (IIS) und alle Webdienste auf einem anderen Laufwerk als dem Systemlaufwerk gefunden werden müssen, können Sie den Pfad für den Installationspfad für die Skype for Business Server Dateien im Dialogfeld Setup ändern. Wenn Sie die Setup Dateien in diesem Pfad installieren, einschließlich OCSCore. msi, werden auch die restlichen Skype for Business Server Dateien auf diesem Laufwerk bereitgestellt. 

5. Lesen Sie die Lizenzbedingungen auf der Seite Endbenutzer-Lizenzvertrag, klicken Sie auf **Ich stimme zu** und anschließend auf **OK**. Dieser Schritt ist erforderlich, um fortfahren zu können.
6. Klicken Sie auf der Seite Bereitstellungs-Assistent auf **Administrator Tools installieren**. 
7. Klicken Sie nach dem erfolgreichen Abschluss der Installation auf **Beenden**.

Verwenden Sie die folgenden Verfahren, um administrative Tools für die Bereitstellung, Konfiguration oder Problembehandlung Ihrer Skype for Business Server Topologie zu öffnen.

- [Bereitstellungs-Assistent](#deployment-wizard)
- [Topologie-Generator](#topology-builder) 
- [Skype for Business Server-Systemsteuerung](#skype-for-business-server-control-panel)
- [Skype for Business Server-Verwaltungsshell](#skype-for-business-server-management-shell)

## <a name="deployment-wizard"></a>Bereitstellungs-Assistent

Verwenden Sie das folgende Verfahren, um den Bereitstellungs-Assistenten lokal zu starten, um Komponentendateien hinzuzufügen oder zu entfernen.

**So starten Sie den Skype for Business Server-Bereitstellungs-Assistenten**

1. Melden Sie sich an dem Computer an, auf dem der Skype for Business Server-Bereitstellungs-Assistent als Mitglied der Gruppe "Domänen-Admins" und der Gruppe "RTCUniversalServerAdmins" installiert ist.
2. Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Skype for Business Server**, und klicken Sie dann auf **Skype for Business Server Bereitstellungs-Assistent**.


## <a name="topology-builder"></a>Topologie-Generator 

Verwenden Sie das folgende Verfahren, um den Topologie-Generator zu öffnen, um die Server zu definieren, die Sie in Ihrer Skype for Business Server Topologie bereitstellen möchten.

**So öffnen Sie den Skype for Business Server Topologie-Generator zum Entwerfen der Topologie**

1. Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.
    > [!NOTE]
    > Sie können eine Topologie mithilfe eines Kontos definieren, das Mitglied der lokalen Benutzergruppe ist, aber zum Lesen, veröffentlichen oder Aktivieren einer Topologie, die zum Installieren von Skype for Business Server auf einem Server erforderlich ist, müssen Sie ein Konto verwenden, das Mitglied der Gruppe "Domänen-Admins" ist, und Th e RTCUniversalServerAdmins-Gruppe mit Vollzugriff auf die Dateifreigabe, die Sie für den Archivierungsdatei Speicher verwenden möchten (d. h., lesen, schreiben und ändern), damit der Topologie-Generator die erforderliche freigegebene Zugriffssteuerungsliste konfigurieren kann ( DACLs) oder ein Konto mit gleichwertigen Benutzerrechten.
 
2. Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Skype for Business Server**, und klicken Sie dann auf **Skype for Business Server Topologie-Generator**.

## <a name="skype-for-business-server-control-panel"></a>Skype for Business Server-Systemsteuerung 

Verwenden Sie eines der folgenden Verfahren, um die Skype for Business Server-Systemsteuerung zu öffnen, um die Konfiguration von Servern, Benutzern, Clients und Geräten in Ihrer Umgebung zu verwalten.

> [!NOTE]
> Sie können ein Benutzerkonto verwenden, das der CsAdministrator-Rolle zugewiesen ist, um eine beliebige Aufgabe in der Skype for Business Server-Systemsteuerung auszuführen. Sie können andere Rollen verwenden, um sich bei der Skype for Business Server-Systemsteuerung anzumelden, um bestimmte Verwaltungsaufgaben auszuführen, abhängig von der Aufgabe, die Sie ausführen müssen. Beispielsweise können Sie csarchivingadministrator "zur Verwaltung der Archivierung in der Skype for Business Server-Systemsteuerung verwenden. Ausführliche Informationen zu Rollen finden Sie unter [Planung für die rollenbasierte Zugriffssteuerung](https://technet.microsoft.com/library/gg425917(v=ocs.15).aspx). Ausführliche Informationen zu den Rollen, die Sie zum Ausführen einer bestimmten Aufgabe verwenden können, finden Sie in der Dokumentation für den Vorgang. 

**So öffnen Sie die Skype for Business Server-Systemsteuerung von einem beliebigen Computer innerhalb der Firewall Ihres Unternehmens**

1. Melden Sie sich von einem Benutzerkonto, das der CsAdministrator-Rolle oder einer anderen Rolle zugewiesen ist, die über entsprechende Benutzerrechte und Berechtigungen für die auszuführende Aufgabe verfügt, bei einem beliebigen Computer in ihrer internen Bereitstellung mit einer minimalen Bildschirmauflösung von 1024 x 768 an.

    > [!IMPORTANT]
    > Wenn Sie einen einfachen Verwaltungs-URL (Uniform Resource Locator) konfiguriert haben, können Sie über einen Internet Browser, der auf einem beliebigen Computer in der Firewall Ihres Unternehmens läuft, auf die Skype for Business Server Systemsteuerung zugreifen. Ausführliche Informationen zum Konfigurieren der einfachen Verwaltungs-URL finden Sie unter [Planning for Simple URLs](https://technet.microsoft.com/library/gg398287(v=ocs.15).aspx) und [Bearbeiten oder konfigurieren einfacher URLs](https://technet.microsoft.com/library/gg398063(v=ocs.15).aspx). 

2. Öffnen Sie ein Browserfenster, und geben Sie die für Ihre Organisation konfigurierte Admin-URL ein.

**So öffnen Sie die Skype for Business Server-Systemsteuerung auf einem Computer mit Skype for Business Server**

1. Melden Sie sich von einem Benutzerkonto, das Mitglied der CsAdministrator-Rolle oder einer anderen Rolle mit entsprechenden Benutzerrechten und Berechtigungen für die auszuführende Aufgabe ist, an einem Computer an, auf dem Sie Skype for Business Server installiert haben, oder mindestens , die Skype for Business Server Verwaltungstools. Zum Konfigurieren von Einstellungen muss der Computer eine minimale Bildschirmauflösung von 1024 x 768 aufweisen.
2. Start Skype for Business Server Systemsteuerung: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, dann auf **Verwaltung**, dann auf **Skype for Business Server**, und klicken Sie dann auf **Skype for Business Server System**Steuerung.

## <a name="skype-for-business-server-management-shell"></a>Skype for Business Server-Verwaltungsshell 

Verwenden Sie das folgende Verfahren, um die Skype for Business Server-Verwaltungsshell zum Verwalten von Servern, Benutzern, Clients und Geräten in Ihrer Umgebung mithilfe der Befehlszeile zu öffnen.

> [!NOTE]
> Sie können ein Benutzerkonto verwenden, das der CsAdministrator-Rolle zugewiesen ist, um eine beliebige Aufgabe in der Skype for Business Server Verwaltungsshell auszuführen. Sie können sich mit anderen Rollen anmelden, um bestimmte Verwaltungsaufgaben auszuführen, abhängig von der Aufgabe, die Sie ausführen müssen. Beispielsweise können Sie csarchivingadministrator "verwenden, um Cmdlets im Zusammenhang mit der Archivierungsverwaltung auszuführen. Ausführliche Informationen zu Rollen finden Sie unter [Planung für die rollenbasierte Zugriffssteuerung](https://technet.microsoft.com/library/gg425917(v=ocs.15).aspx). Ausführliche Informationen zu den Rollen, die Sie zum Ausführen eines bestimmten Cmdlets verwenden können, finden Sie in der Dokumentation für das Cmdlet.<br/><br/>Sie können auch bestimmte Cmdlets mithilfe eines Benutzerkontos in den Gruppen RTCUniversalServerAdmins, RTCUniversalUserAdmins oder RTCUniversalReadOnlyAdmins ausführen, abhängig vom Cmdlet. 

**So öffnen Sie Skype for Business Server Management Shell**

Wenn Sie ein Windows PowerShell Fenster anstelle der Skype for Business Server-Verwaltungsshell öffnen, können Sie die Skype for Business Server-Cmdlets standardmäßig nicht ausführen. Geben Sie an der Windows PowerShell-Eingabeaufforderung Folgendes ein, um die Skype for Business Server-Cmdlets in Windows PowerShell auszuführen:

`Import-Module Lync`

Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for Business Server**, und klicken Sie dann auf **Skype for Business Server Management Shell**.
