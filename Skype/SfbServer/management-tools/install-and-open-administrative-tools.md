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
description: In diesem Thema wird beschrieben, wie Sie die Verwaltungstools installieren und öffnen, die Sie für die Bereitstellung und Verwaltung von Skype for Business benötigen.
ms.openlocfilehash: c720aba3998df8742406f4c9954f523b20e9af5f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816554"
---
# <a name="install-and-open-administrative-tools"></a>Installieren und Öffnen von Verwaltungstools

In diesem Thema wird beschrieben, wie Sie die Verwaltungstools installieren, die Sie für die Bereitstellung und Verwaltung von Skype for Business Server benötigen. Die Verwaltungstools werden standardmäßig auf jedem Server installiert, auf dem Skype for Business Server ausgeführt wird. Darüber hinaus können Sie die Verwaltungstools auf anderen Computern installieren, beispielsweise in dedizierten Verwaltungskonsolen. Wir empfehlen dringend, dass Sie die Verwaltungstools auf einem Computer installieren, der sich in der gleichen Domäne oder Gesamtstruktur wie die von Ihnen erstellte Skype for Business Server-Bereitstellung befindet, um sicherzustellen, dass die Schritte zur Vorbereitung der Active Directory-Domänendienste bereits abgeschlossen sind. Damit können Sie später die Verwaltungstools auf diesem Computer verwenden, um Ihre Topologie zu veröffentlichen. Stellen Sie außerdem sicher, dass Sie die erforderlichen Voraussetzungen überprüfen, bevor Sie die Skype for Business Server-Verwaltungstools installieren oder verwenden. Weitere Informationen finden Sie in der Dokumentation zu den Anforderungen in [Skype for Business Server 2019](../../SfBServer2019/plan/system-requirements.md) oder [Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md).
 
> [!Important]
> Wenn Ihre Organisation erfordert, dass Sie Internet Informationsdienste (IIS) und alle Webdienste auf einem anderen Laufwerk als dem Systemlaufwerk finden, können Sie den Pfad für den Installationspfad für die Skype for Business Server-Dateien im Dialogfeld einrichten ändern. Wenn Sie die Setup Dateien in diesem Pfad installieren, einschließlich OCSCore. msi, werden die restlichen Skype for Business Server-Dateien ebenfalls auf diesem Laufwerk bereitgestellt. 

## <a name="to-install-the-administrative-tools"></a>So installieren Sie die Verwaltungstools

1. Melden Sie sich als lokaler Administrator (Mindestanforderung) an dem Computer an, auf dem Sie die Verwaltungstools installieren möchten. Wenn Sie in Windows als Standardbenutzer angemeldet sind und die Benutzerkontensteuerung (User Account Control, UAC) aktiviert ist, werden Sie aufgefordert, den lokalen Administrator oder einen Domänen äquivalenten Benutzernamen und ein Kennwort einzugeben.
2. Suchen Sie das Installationsmedium auf dem Computer, und doppelklicken Sie dann auf \Setup\amd64\Setup.exe.
3. Wenn Sie aufgefordert werden, die Microsoft Visual C++-Distribution zu installieren, klicken Sie auf **Ja**.
4. Klicken Sie auf der Seite Installationsspeicherort auf **OK**. Ändern Sie diesen Pfad zu einem anderen Speicherort oder Laufwerk, wenn die Dateien an einem anderen Speicherort installiert werden müssen.

    > [!Important]
    > Wenn Ihre Organisation erfordert, dass Sie Internet Informationsdienste (IIS) und alle Webdienste auf einem anderen Laufwerk als dem Systemlaufwerk finden, können Sie den Pfad für den Installationspfad für die Skype for Business Server-Dateien im Dialogfeld einrichten ändern. Wenn Sie die Setup Dateien in diesem Pfad installieren, einschließlich OCSCore. msi, werden auch die restlichen Skype for Business Server-Dateien auf diesem Laufwerk bereitgestellt. 

5. Überprüfen Sie auf der Seite Endbenutzer-Lizenzvertrag die Lizenzbedingungen, klicken Sie auf **Ich akzeptiere**, und klicken Sie dann auf **OK**. Dieser Schritt ist erforderlich, bevor Sie fortfahren können.
6. Klicken Sie auf der Seite Deployment-Assistent auf **Administrator Tools installieren**. 
7. Wenn die Installation erfolgreich abgeschlossen wurde, klicken Sie auf **Beenden**.

Führen Sie die folgenden Verfahren aus, um die Verwaltungstools für die Bereitstellung, Konfiguration oder Problembehandlung Ihrer Skype for Business Server-Topologie zu öffnen.

- [Bereitstellungs-Assistent](#deployment-wizard)
- [Topologie-Generator](#topology-builder) 
- [Skype for Business Server-Systemsteuerung](#skype-for-business-server-control-panel)
- [Skype for Business Server-Verwaltungsshell](#skype-for-business-server-management-shell)

## <a name="deployment-wizard"></a>Bereitstellungs-Assistent

Gehen Sie wie folgt vor, um den Bereitstellungs-Assistenten lokal zu starten, um Komponentendateien hinzuzufügen oder zu entfernen.

**So starten Sie den Skype for Business Server-Bereitstellungs-Assistenten**

1. Melden Sie sich bei dem Computer an, auf dem der Skype for Business Server-Bereitstellungs-Assistent als Mitglied der Gruppe "Domänen-Admins" und der Gruppe "RTCUniversalServerAdmins" installiert ist.
2. Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for Business Server**, und klicken Sie dann auf **Skype for Business Server-Bereitstellungs-Assistent**.


## <a name="topology-builder"></a>Topologie-Generator 

Gehen Sie wie folgt vor, um den Topologie-Generator zu öffnen, um die Server zu definieren, die Sie in Ihrer Skype for Business Server-Topologie bereitstellen möchten.

**So öffnen Sie den Skype for Business Server-Topologie-Generator zum Entwerfen der Topologie**

1. Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.
    > [!NOTE]
    > Sie können eine Topologie mithilfe eines Kontos definieren, das ein Mitglied der lokalen Benutzergruppe ist, aber zum Lesen, veröffentlichen oder Aktivieren einer Topologie, die für die Installation von Skype for Business Server auf einem Server erforderlich ist, müssen Sie ein Konto verwenden, das ein Mitglied der Gruppe "Domain Admins" und "th" ist. e RTCUniversalServerAdmins-Gruppe, die über Vollzugriffsberechtigungen (also lesen, schreiben und ändern) für die Dateifreigabe verfügt, die Sie für den Archivierungsdatei Speicher verwenden werden, damit der Topologie-Generator die erforderliche freigegebene Zugriffssteuerungsliste konfigurieren kann ( DACLs) oder ein Konto mit entsprechenden Benutzerrechten.
 
2. Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for Business Server**, und klicken Sie dann auf **Skype for Business Server Topology Builder**.

## <a name="skype-for-business-server-control-panel"></a>Skype for Business Server-Systemsteuerung 

Führen Sie eines der folgenden Verfahren aus, um das Skype for Business Server Control Panel zu öffnen, um die Konfiguration von Servern, Benutzern, Clients und Geräten in Ihrer Umgebung zu verwalten.

> [!NOTE]
> Sie können ein Benutzerkonto verwenden, das der CsAdministrator-Rolle zugewiesen ist, um beliebige Aufgaben im Skype for Business Server-Control Panel durchzuführen. Sie können andere Rollen verwenden, um sich bei der Skype for Business Server-Systemsteuerung anzumelden, um bestimmte Verwaltungsaufgaben auszuführen, abhängig von der Aufgabe, die Sie ausführen müssen. So können Sie beispielsweise CSArchivingAdministrator verwenden, um die Archivierung im Skype Control Panel für Unternehmen Server zu verwalten. Details zu Rollen finden Sie unter [Planen der rollenbasierten Zugriffssteuerung](https://technet.microsoft.com/en-us/library/gg425917(v=ocs.15).aspx). Details zu den Rollen, die Sie zum Ausführen einer bestimmten Aufgabe verwenden können, finden Sie in der Dokumentation der Aufgabe. 

**So öffnen Sie die Skype for Business Server-Systemsteuerung von einem beliebigen Computer in der Firewall Ihrer Organisation**

1. Melden Sie sich bei einem Benutzerkonto, das der Rolle CsAdministrator oder einer anderen Rolle zugewiesen ist, die über die entsprechenden Benutzerrechte und Berechtigungen für die auszuführende Aufgabe verfügt, bei einem beliebigen Computer in ihrer internen Bereitstellung mit einer Mindestauflösung von 1024 x 768 an.

    > [!IMPORTANT]
    > Wenn Sie eine einfache URL (Uniform Resource Locator) für die Verwaltung konfiguriert haben, können Sie über einen Internet Browser, der auf einem beliebigen Computer in der Firewall Ihrer Organisation ausgeführt wird, auf das Control Panel für Skype for Business Server zugreifen. Details zum Konfigurieren der einfachen URL für die Verwaltung finden Sie unter [Planen einfacher URLs](https://technet.microsoft.com/en-us/library/gg398287(v=ocs.15).aspx) und [Bearbeiten oder konfigurieren einfacher URLs](https://technet.microsoft.com/en-us/library/gg398063(v=ocs.15).aspx). 

2. Öffnen Sie ein Browserfenster, und geben Sie dann die für Ihre Organisation konfigurierte Administrator-URL ein.

**So öffnen Sie das Skype for Business Server Control Panel auf einem Computer, auf dem Skype for Business Server läuft**

1. Melden Sie sich bei einem Benutzerkonto, das Mitglied der Rolle CsAdministrator oder einer anderen Rolle mit den entsprechenden Benutzerrechten und Berechtigungen für die auszuführende Aufgabe ist, an einem Computer an, auf dem Sie Skype for Business Server installiert haben, oder mindestens , die Skype for Business Server-Verwaltungstools. Zum Konfigurieren der Einstellungen muss der Computer mindestens eine Bildschirmauflösung von 1024 x 768 aufweisen.
2. Starten Sie die Skype for Business Server-Systemsteuerung: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, zeigen Sie auf **Verwaltung**, zeigen Sie auf **Skype for Business Server**, und klicken Sie dann auf **Skype for Business Server Control Panel**.

## <a name="skype-for-business-server-management-shell"></a>Skype for Business Server-Verwaltungsshell 

Gehen Sie wie folgt vor, um die Skype for Business Server-Verwaltungsshell zum Verwalten von Servern, Benutzern, Clients und Geräten in Ihrer Umgebung über die Befehlszeile zu öffnen.

> [!NOTE]
> Sie können ein Benutzerkonto verwenden, das der CsAdministrator-Rolle zugewiesen ist, um beliebige Aufgaben in der Skype for Business Server-Verwaltungsshell durchzuführen. Sie können sich mit anderen Rollen anmelden, um bestimmte Verwaltungsaufgaben auszuführen, abhängig von der Aufgabe, die Sie ausführen müssen. So können Sie beispielsweise CSArchivingAdministrator verwenden, um Cmdlets für die Archivierungsverwaltung auszuführen. Details zu Rollen finden Sie unter [Planen der rollenbasierten Zugriffssteuerung](https://technet.microsoft.com/en-us/library/gg425917(v=ocs.15).aspx). Details zu den Rollen, die Sie zum Ausführen eines bestimmten Cmdlets verwenden können, finden Sie in der Dokumentation für das Cmdlet.<br/><br/>Sie können bestimmte Cmdlets auch ausführen, indem Sie je nach Cmdlet ein Benutzerkonto in den Gruppen RTCUniversalServerAdmins, RTCUniversalUserAdmins oder RTCUniversalReadOnlyAdmins verwenden. 

**So öffnen Sie die Skype for Business Server-Verwaltungsshell**

Wenn Sie ein Windows PowerShell-Fenster anstelle der Skype for Business Server-Verwaltungsshell öffnen, können Sie die Skype for Business Server-Cmdlets standardmäßig nicht ausführen. Wenn Sie die Skype for Business Server-Cmdlets in Windows PowerShell ausführen möchten, geben Sie Folgendes an der Windows PowerShell-Eingabeaufforderung ein:

`Import-Module Lync`

Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for Business Server**, und klicken Sie dann auf **Skype for Business Server-Verwaltungsshell**.
