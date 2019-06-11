---
title: 'Lync Server 2013: Aktivieren von Benutzern für Enterprise-VoIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable users for Enterprise Voice
ms:assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413011(v=OCS.15)
ms:contentKeyID: 48185800
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d94b2ad348bc1d086716deed2beef0dcfbe78e2b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832285"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-users-for-enterprise-voice-in-lync-server-2013"></a>Aktivieren von Benutzern für Enterprise-VoIP in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Nachdem Sie Dateien für einen oder mehrere Vermittlungsserver installiert, das Routing für ausgehende Anrufe konfiguriert und optional mindestens eine erweiterte Enterprise-VoIP-Funktion bereitgestellt haben, können Sie die folgenden Verfahren verwenden, um einem Benutzer das tätigen von Anrufen mithilfe von Enterprise-VoIP zu ermöglichen:

<div>


> [!NOTE]  
> Von den folgenden Verfahren kann nur die erste mithilfe der lync Server-Systemsteuerung ausgeführt werden. Für die restlichen Verfahren können Sie nur die lync Server-Verwaltungsshell verwenden.



</div>

  - Aktivieren Sie das Benutzerkonto für Enterprise-VoIP.

  - (Optional) Zuweisen einer benutzerspezifischen VoIP-Richtlinie für das Benutzerkonto.

  - (Optional) Zuweisen eines benutzerspezifischen Satzes mit Wähleinstellungen für das Benutzerkonto.

<div>

## <a name="to-enable-a-user-account-for-enterprise-voice"></a>So aktivieren Sie ein Benutzerkonto für Enterprise-VoIP

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4.  Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das aktiviert werden soll und klicken Sie dann auf **Suchen**.

5.  Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie für Enterprise-VoIP aktivieren möchten.

6.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

7.  Klicken Sie auf der Seite **lync Server-Benutzer bearbeiten** unter **Telefonie**auf **Enterprise-VoIP**.

8.  Klicken Sie auf **Anschluss-URI** und geben Sie eine eindeutige, normalisierte Telefonnummer ein (beispielsweise tel:+14255550200).

9.  Klicken Sie auf **Commit ausführen**.

Um die Aktivierung eines Benutzers für Enterprise-VoIP abzuschließen, stellen Sie sicher, dass dem Benutzer eine VoIP-Richtlinie und ein Wählplan zugewiesen ist, egal ob Global (standardmäßig zugewiesen) oder benutzerspezifisch.

Standardmäßig werden allen Benutzern eine globale VoIP-Richtlinie und ein Wählplan zugewiesen. Wenn auf Standortebene eine VoIP-Richtlinie für den Standort vorhanden ist, der das Benutzerkonto verwaltet, gelten diese Standortrichtlinien automatisch für alle Benutzer. Führen Sie die Cmdlets **Grant-CsVoicePolicy** und **Grant-CsDialPlan** aus, um eine benutzerspezifische VoIP-Richtlinie oder einen Wählplan für einen Benutzer anzuwenden. Ausführliche Informationen finden Sie in der Dokumentation zur [lync Server 2013-Verwaltungsshell](lync-server-2013-lync-server-management-shell.md) .

</div>

<div>

## <a name="voice-policy-assignment"></a>Zuweisen einer VoIP-Richtlinie

VoIP-Richtlinien auf globaler und Websiteebene werden automatisch allen Benutzerkonten zugewiesen, die für Enterprise-VoIP aktiviert sind. Sie können auch VoIP-Richtlinien erstellen, die für spezielle Benutzer oder Gruppen gelten. Diese benutzerbezogenen Richtlinien müssen den Benutzern oder Gruppen explizit zugewiesen werden. Wenn Sie die Global-oder Website-VoIP-Richtlinie für alle Benutzer verwenden möchten, die für Enterprise-VoIP aktiviert sind, können Sie diesen Abschnitt überspringen und weiter unten in diesem Thema den Abschnitt "Wähl Plan Zuweisung" auswählen.

<div>

## <a name="to-assign-a-user-specific-voice-policy"></a>So weisen Sie eine benutzerspezifische VoIP-Richtlinie zu

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie den folgenden Befehl an der Eingabeaufforderung aus, um einem Benutzer eine vorhandene VoIP-Benutzerrichtlinie zuzuweisen:
    
        Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
    
    Beispiel:
    
        Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
    
    In diesem Beispiel erhält der Benutzer mit dem Anzeigenamen Bob Kelly die VoIP-Richtlinie mit dem Namen **VoicePolicyJapan**.

Details zum Zuweisen einer benutzerspezifischen VoIP-Richtlinie oder zum Ausführen des Cmdlets **Grant-CsVoicePolicy** finden Sie in der Dokumentation zur [lync Server 2013-Verwaltungsshell](lync-server-2013-lync-server-management-shell.md) .

</div>

</div>

<span id="BKMK_DialPlanAssignment"></span>

<div>

## <a name="dial-plan-assignment"></a>Zuweisen eines Wählplans

Um die Konfiguration des Benutzerkontos für Benutzer von Enterprise-VoIP oder Benutzer von Einwahlkonferenzen abzuschließen, muss dem Benutzer ein Wählplan zugewiesen sein. Benutzerkonten verwenden automatisch den globalen Wählplan oder, falls vorhanden, den Wählplan auf Standortebene, wenn Sie nicht jedem Benutzer explizit einen vorhandenen Wählplan zuweisen. Wenn Sie den Global-oder Website Wähl Plan für alle Benutzer verwenden möchten, die für Enterprise-VoIP aktiviert sind, können Sie diesen Abschnitt überspringen.

<div>

## <a name="to-assign-a-dial-plan"></a>So weisen Sie einen Wählplan zu

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie den folgenden Befehl an der Eingabeaufforderung aus, um einen benutzerspezifischen Wählplan zuzuweisen:
    
        Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
    
    Beispiel:
    
        Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
    
    In diesem Beispiel erhält der Benutzer mit dem Anzeigenamen Bob Kelly den Benutzer Wählplan mit dem Namen **DialPlanJapan**.

Details zum Zuweisen von Benutzer Wählplänen oder zum Ausführen des Cmdlets **Grant-CsDialPlan** finden Sie in der Dokumentation zur [lync Server 2013-Verwaltungsshell](lync-server-2013-lync-server-management-shell.md) .

</div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Deaktivieren eines Benutzers für Enterprise-VoIP in lync Server 2013](lync-server-2013-disable-a-user-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

