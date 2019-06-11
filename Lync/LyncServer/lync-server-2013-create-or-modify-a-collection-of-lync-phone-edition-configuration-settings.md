---
title: Erstellen oder Ändern einer Sammlung von lync Phone Edition-Konfigurationseinstellungen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a collection of Lync Phone Edition configuration settings
ms:assetid: 6cf714af-8f57-4a71-89ad-0a776302b2ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688086(v=OCS.15)
ms:contentKeyID: 49733683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3012ffeeb8dd4559ee05a45dd07becefd099691
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832816"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a>Erstellen oder Ändern einer Sammlung von lync Phone Edition-Konfigurationseinstellungen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Wenn Sie lync Server installieren, erhalten Sie eine globale Sammlung von lync Phone Edition-Einstellungen. Diese Einstellungen gelten für alle Geräte, auf denen lync Phone Edition in Ihrer Bereitstellung ausgeführt wird. Sie können diese Einstellungen jederzeit ändern. Sie können auch eine neue Sammlung von Einstellungen einrichten, die für die Geräte in einer bestimmten Website gelten. Websiteeinstellungen haben Vorrang vor globalen Einstellungen.

Die Konfigurationseinstellungen bestehen aus dem Sammlungsnamen, dem Bereich (Global oder Website), der SIP-Sicherheitseinstellung, dem Protokolliergrad, der sprach Dienstleistungsqualität (QoS), der Einstellung der Telefonsperre und den Details der Telefonsperre, also wie lange die a) die persönliche Identifikationsnummer entsperren ( PIN) muss sein und b) das Telefon bleibt inaktiv, bevor es sich selbst sperrt.

<div>

## <a name="to-create-a-collection-of-lync-phone-edition-configuration-settings-or-edit-settings-for-an-existing-collection"></a>So erstellen Sie eine Sammlung von lync Phone Edition-Konfigurationseinstellungen oder Bearbeiten von Einstellungen für eine vorhandene Sammlung

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf die Navigationsschaltfläche **Gerätekonfiguration** .

4.  Führen Sie auf der Seite **Device Configuration** eine der folgenden Aktionen aus:
    
      - Wenn Sie eine neue Sammlung von lync Phone Edition-Konfigurationseinstellungen erstellen möchten, klicken Sie auf **neu**, wählen Sie eine Website aus, klicken Sie auf **OK**, überprüfen Sie die Standardeinstellungen, und nehmen Sie bei Bedarf Änderungen vor.
    
      - Wenn Sie eine der Einstellungen in einer vorhandenen Sammlung bearbeiten möchten, klicken Sie auf die Sammlung, klicken Sie auf das Menü **Bearbeiten** , klicken Sie auf **Details anzeigen**, und nehmen Sie dann die gewünschten Änderungen vor.
        
        <div>
        

        > [!TIP]
        > Wenn Sie zur Verwendung der Standardeinstellungen für die globale Sammlung zurückkehren möchten, klicken Sie auf die globale Sammlung, klicken Sie auf das Menü <STRONG>Bearbeiten</STRONG> , klicken Sie auf <STRONG>Löschen</STRONG>, und klicken Sie dann auf <STRONG>OK</STRONG>. Dadurch wird die globale Sammlung nicht gelöscht; die Einstellungen werden nur auf die Standardeinstellungen zurückgesetzt.

        
        </div>

5.  Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="creating-new-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a>Erstellen neuer lync Phone Edition-Konfigurationseinstellungen mithilfe von Windows PowerShell-Cmdlets

Sie können die Konfigurationseinstellungen für lync Phone Edition (nur im Website Bereich) mithilfe von Windows PowerShell und dem Cmdlet **New-CsUCPhoneConfiguration** erstellen. Sie können dieses Cmdlet in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.

<div>

## <a name="to-create-new-lync-phone-edition-configuration-settings-that-use-the-default-values"></a>So erstellen Sie neue lync Phone Edition-Konfigurationseinstellungen, die die Standardwerte verwenden

  - Dieser Befehl erstellt einen neuen Satz von UC-Telefon Konfigurationseinstellungen für die Website "Redmond":
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond"
    
    Da im vorherigen Befehl keine weiteren Parameter (außer dem obligatorischen Identity-Parameter) angegeben wurden, werden in der neuen Auflistung von Konfigurationseinstellungen für alle Eigenschaften die Standardwerte verwendet.

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-new-lync-phone-edition-configuration-settings"></a>So ändern Sie einen einzelnen Eigenschaftswert beim Erstellen neuer lync Phone Edition-Konfigurationseinstellungen

  - Um Einstellungen zu erstellen, die andere Eigenschaftswerte verwenden, geben Sie einfach den entsprechenden Parameter und Parameterwert ein. Wenn Sie beispielsweise eine Sammlung von UC-Telefon Konfigurationseinstellungen erstellen möchten, die standardmäßig Telefon sperren erfordern, verwenden Sie einen Befehl wie den folgenden:
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-new-lync-phone-edition-configuration-settings"></a>So ändern Sie beim Erstellen neuer lync Phone Edition-Konfigurationseinstellungen mehrere Eigenschaftswerte

  - Mehrere Eigenschaftswerte können geändert werden, indem Sie mehrere Parameter angeben. Mit diesem Befehl wird beispielsweise die Telefon Verriegelung erzwungen und die minimale PIN-Länge auf 8 Ziffern festgelegt:
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True -MinPhonePinLength 8

</div>

Ausführliche Informationen finden Sie unter [New-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398445(v=OCS.15)).

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Löschen einer vorhandenen Sammlung von lync Phone Edition-Konfigurationseinstellungen in lync Server 2013](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[Konfigurieren von Sicherheitseinstellungen für lync Phone Edition in lync Server 2013](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[Erzwingen der Telefon Sperrung in lync Server 2013](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

