---
title: Erstellen oder Ändern einer Sammlung von lync Phone Edition Konfigurationseinstellungen
description: Erstellen oder ändern Sie eine Sammlung von lync-Phone Edition Konfigurationseinstellungen.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of Lync Phone Edition configuration settings
ms:assetid: 6cf714af-8f57-4a71-89ad-0a776302b2ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688086(v=OCS.15)
ms:contentKeyID: 49733683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82a4becadf581ec965952e507c3eb2839b622d9f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578251"
---
# <a name="create-or-modify-a-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a>Erstellen oder Ändern einer Sammlung von lync Phone Edition Konfigurationseinstellungen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-23_

Wenn Sie lync Server installieren, erhalten Sie eine globale Sammlung von lync Phone Edition-Einstellungen. Diese Einstellungen gelten für alle Geräte, auf denen lync Phone Edition in Ihrer Bereitstellung. Sie können diese Einstellungen jederzeit ändern. Sie können auch eine neue Auflistung der Einstellungen einrichten, die für die Geräte an einem bestimmten Standort gelten. Standorteinstellungen haben Vorrang vor globalen Einstellungen.

Zu den Konfigurationseinstellungen zählen der Auflistungsname, der Geltungsbereich (global oder standortweit), die SIP-Sicherheitseinstellung, der Protokolliergrad, die Stufe der VoIP-Dienstqualität (QoS), das Einstellen der Telefonsperre sowie Details zur Telefonsperre, d. h., a) wie lang die Persönliche Identifikationsnummer (PIN-Nummer) sein muss, und b) nach wie viel Zeit im Ruhezustand das Telefon automatisch gesperrt wird.

<div>

## <a name="to-create-a-collection-of-lync-phone-edition-configuration-settings-or-edit-settings-for-an-existing-collection"></a>So erstellen Sie eine Sammlung von lync Phone Edition Konfigurationseinstellungen oder Bearbeitungseinstellungen für eine vorhandene Sammlung

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients** und dann auf die Navigationsschaltfläche **Gerätekonfiguration**.

4.  Führen Sie auf der Seite **Gerätekonfiguration** einen der folgenden Schritte aus:
    
      - Um eine neue Sammlung von lync Phone Edition Konfigurationseinstellungen zu erstellen, klicken Sie auf **neu**, wählen Sie einen Standort aus, klicken Sie auf **OK**, überprüfen Sie die Standardeinstellungen, und nehmen Sie bei Bedarf Änderungen vor.
    
      - Zum Bearbeiten von Einstellungen in einer vorhandenen Auflistung klicken Sie auf die Auflistung und dann auf das Menü **Bearbeiten**. Wählen Sie **Details anzeigen** und nehmen Sie Ihre Änderungen vor.
        
        <div>
        

        > [!TIP]
        > Wenn Sie wieder die Standardeinstellungen für die globale Auflistung verwenden möchten, klicken Sie auf das Menü <STRONG>Bearbeiten</STRONG>, dann auf <STRONG>Löschen</STRONG> und schließlich auf <STRONG>OK</STRONG>. Hierdurch wird die globale Auflistung nicht gelöscht; die Einstellungen werden lediglich auf die Standardwerte zurückgesetzt.

        
        </div>

5.  Klicken Sie auf **Commit**.

</div>

<div>

## <a name="creating-new-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a>Erstellen neuer lync Phone Edition-Konfigurationseinstellungen mithilfe von Windows PowerShell-Cmdlets

Sie können lync Phone Edition Konfigurationseinstellungen können (nur auf Standortebene) mithilfe von Windows PowerShell und dem **New-CsUCPhoneConfiguration-** Cmdlet erstellt werden. Sie können dieses Cmdlet in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-create-new-lync-phone-edition-configuration-settings-that-use-the-default-values"></a>So erstellen Sie neue lync Phone Edition-Konfigurationseinstellungen, die die Standardwerte verwenden

  - Über diesen Befehl wird ein neuer Satz mit Konfigurationseinstellungen für das UC-Telefon für den Standort in Redmond erstellt:
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond"
    
    Da im vorstehenden Befehl (abgesehen vom obligatorischen Identity-Parameter) keine Parameter angegeben wurden, verwendet die neue Auflistung mit Konfigurationseinstellungen für alle enthaltenen Eigenschaften die Standardwerte.

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-new-lync-phone-edition-configuration-settings"></a>So ändern Sie einen einzelnen Eigenschaftswert beim Erstellen neuer lync Phone Edition-Konfigurationseinstellungen

  - Zum Erstellen von Einstellungen, die verschiedene Eigenschaftswerte verwenden, geben Sie einfach den entsprechenden Parameter und den Parameterwert an. Um beispielsweise eine Auflistung von Konfigurationseinstellungen für UC-Telefone zu erstellen, für die standardmäßig die Telefonsperre erforderlich ist, müssen Sie einen Befehl wie den folgenden verwenden:
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-new-lync-phone-edition-configuration-settings"></a>So ändern Sie beim Erstellen neuer lync Phone Edition-Konfigurationseinstellungen mehrere Eigenschaftswerte

  - Mehrere Eigenschaftswerte können durch die Angabe mehrerer Parameter geändert werden. Der folgende Befehl beispielsweise erzwingt die Telefonsperre und legt gleichzeitig als minimale PIN-Länge 8 Ziffern fest:
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True -MinPhonePinLength 8

</div>

Ausführliche Informationen finden Sie unter [New-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398445(v=OCS.15)).

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Löschen einer vorhandenen Sammlung von lync Phone Edition Konfigurationseinstellungen in lync Server 2013](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[Konfigurieren von Sicherheitseinstellungen für lync Phone Edition in lync Server 2013](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[Erzwingen der Telefonsperre in lync Server 2013](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

