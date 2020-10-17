---
title: 'Lync Server 2013: Aktivieren von Benutzern für Enterprise-VoIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for Enterprise Voice
ms:assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413011(v=OCS.15)
ms:contentKeyID: 48185800
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d03f47cbe637e2c6fe6a0466b73a3588b842d6e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501042"
---
# <a name="enable-users-for-enterprise-voice-in-lync-server-2013"></a>Aktivieren von Benutzern für Enterprise-VoIP in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

Nachdem Sie Dateien für einen oder mehrere Vermittlungsserver installiert, das Routing für ausgehende Anrufe konfiguriert und optional eine oder mehrere erweiterte Enterprise-VoIP-Funktionen bereitgestellt haben, können Sie die folgenden Verfahren verwenden, um Benutzern das tätigen von Anrufen mithilfe von Enterprise-VoIP zu ermöglichen:

<div>


> [!NOTE]  
> In den folgenden Verfahren kann nur der erste mithilfe von lync Server-Systemsteuerung ausgeführt werden. Für die restlichen Verfahren können Sie nur lync Server-Verwaltungsshell verwenden.



</div>

  - Aktivieren Sie das Benutzerkonto für Enterprise-VoIP.

  - Optional Weisen Sie dem Benutzerkonto eine benutzerspezifische VoIP-Richtlinie zu.

  - Optional Weisen Sie dem Benutzerkonto benutzerspezifische Wähleinstellungen zu.

<div>

## <a name="to-enable-a-user-account-for-enterprise-voice"></a>So aktivieren Sie ein Benutzerkonto für Enterprise-VoIP

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4.  Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das aktiviert werden soll, und klicken Sie dann auf **Suchen**.

5.  Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie für Enterprise-VoIP aktivieren möchten.

6.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

7.  Klicken Sie auf der Seite **Lync Server-Benutzer bearbeiten** unter **Telefonie** auf **Enterprise-VoIP**.

8.  Klicken Sie auf **Leitungs-URI**, und geben Sie eine eindeutige, normalisierte Telefonnummer ein (beispielsweise Tel: + 14255550200).

9.  Klicken Sie auf **Commit ausführen**.

Um die Aktivierung eines Benutzers für Enterprise-VoIP abzuschließen, müssen Sie sicherstellen, dass dem Benutzer eine VoIP-Richtlinie und ein Wählplan zugewiesen ist, sei es global (standardmäßig zugewiesen) oder benutzerspezifisch.

Standardmäßig werden allen Benutzern eine globale VoIP-Richtlinie und Wähleinstellungen zugewiesen. Wenn eine VoIP-Richtlinie oder ein Wählplan auf Standortebene für den Standort vorhanden ist, auf dem das Benutzerkonto verwaltet wird, werden diese Website Richtlinien automatisch auf den Benutzer angewendet. Um eine VoIP-Richtlinie auf Benutzerbasis oder einen Wählplan auf einen Benutzer anzuwenden, müssen Sie die Cmdlets **Grant-CsVoicePolicy** und **Grant-CsDialPlan** ausführen. Ausführliche Informationen finden Sie in der Dokumentation zur [lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) .

</div>

<div>

## <a name="voice-policy-assignment"></a>Zuweisung von VoIP-Richtlinien

VoIP-Richtlinien auf globaler und Standortebene werden automatisch allen Benutzerkonten zugewiesen, die für Enterprise-VoIP aktiviert sind. Sie können auch VoIP-Richtlinien erstellen, die für bestimmte Benutzer oder Gruppen gelten. Diese benutzerspezifischen Richtlinien müssen den Benutzern oder Gruppen explizit zugewiesen werden. Wenn Sie die Richtlinie "Global" oder "Standort VoIP" für alle Benutzer verwenden möchten, die für Enterprise-VoIP aktiviert sind, können Sie diesen Abschnitt überspringen und weiter unten in diesem Thema den Abschnitt "Wähl Plan Zuweisung" fortsetzen.

<div>

## <a name="to-assign-a-user-specific-voice-policy"></a>So weisen Sie eine benutzerspezifische VoIP-Richtlinie zu

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie den folgenden Befehl an der Eingabeaufforderung aus, um einem Benutzer eine vorhandene VoIP-Benutzerrichtlinie zuzuweisen:
    
        Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
    
    Beispiel:
    
        Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
    
    In diesem Beispiel wird dem Benutzer mit dem Anzeigenamen Bob Kelly die VoIP-Richtlinie mit dem Namen **voicepolicyjapan zugewiesen**zugewiesen.

Ausführliche Informationen zum Zuweisen einer benutzerspezifischen VoIP-Richtlinie oder zum Ausführen des **Grant-CsVoicePolicy-** Cmdlets finden Sie in der Dokumentation zur [lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) .

</div>

</div>

<span id="BKMK_DialPlanAssignment"></span>

<div>

## <a name="dial-plan-assignment"></a>Wähl Plan Zuweisung

Für den Abschluss der Benutzerkontokonfiguration für Benutzer von Enterprise-VoIP oder Benutzer von Einwahlkonferenzen müssen dem Benutzer Wähleinstellungen zugewiesen werden. Benutzerkonten verwenden automatisch den globalen Wählplan oder, falls vorhanden, den Wählplan auf Standortebene, wenn Sie nicht explizit einen vorhandenen Wählplan auf der Basis eines einzelnen Benutzers zuweisen. Wenn Sie den globalen oder den Standort Wähl Plan für alle Benutzer verwenden möchten, die für Enterprise-VoIP aktiviert sind, können Sie diesen Abschnitt überspringen.

<div>

## <a name="to-assign-a-dial-plan"></a>So weisen Sie Wähleinstellungen zu

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie den folgenden Befehl an der Eingabeaufforderung aus, um benutzerspezifische Wähleinstellungen zuzuweisen:
    
        Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
    
    Beispiel:
    
        Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
    
    In diesem Beispiel wird dem Benutzer mit dem Anzeigenamen Bob Kelly der Benutzer Wähl Plan mit dem Namen **dialplanjapan zugewiesen**zugewiesen.

Ausführliche Informationen zum Zuweisen eines Benutzer Wähl Plans oder zum Ausführen des **Grant-CsDialPlan-** Cmdlets finden Sie in der Dokumentation zur [lync Server 2013-Verwaltungsshell](lync-server-2013-lync-server-management-shell.md) .

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

