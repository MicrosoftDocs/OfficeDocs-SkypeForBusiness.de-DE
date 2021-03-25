---
title: Definieren von Normalisierungsregeln in Skype for Business Server
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
description: 'Skype for Business #A0 verwenden .NET Framework Ausdrücke, um gewählte Telefonnummern in das E.164-Format zu übersetzen. Anders ausgedrückt: Normalisierungsregeln verwenden die von einem Benutzer gewählte Telefonnummer und konvertieren diese in das intern von Skype for Business Server verwendete Format. Jedem Wählplan muss mindestens eine Normalisierungsregel zugewiesen werden.'
ms.openlocfilehash: 1be34e5c40a4da4e9def4de294ece134f2fe229d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120917"
---
# <a name="defining-normalization-rules-in-skype-for-business-server"></a>Definieren von Normalisierungsregeln in Skype for Business Server

Skype for Business #A0 verwenden .NET Framework Ausdrücke, um gewählte Telefonnummern in das E.164-Format zu übersetzen. Anders ausgedrückt: Normalisierungsregeln verwenden die von einem Benutzer gewählte Telefonnummer und konvertieren diese in das intern von Skype for Business Server verwendete Format. Jedem Wählplan muss mindestens eine Normalisierungsregel zugewiesen werden.

Weitere Informationen zu Normalisierungsregeln finden Sie unter [Dial plans and normalization rules](/previous-versions/office/lync-server-2013/lync-server-2013-dial-plans-and-normalization-rules).

Weitere Informationen zum Schreiben regulärer Ausdrücke finden Sie unter [.NET Framework Reguläre Ausdrücke](/dotnet/standard/base-types/regular-expressions).

Mithilfe einer der beiden folgenden Methoden können Sie eine Übersetzungsregel definieren oder bearbeiten:
- [  ](#create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule) Verwenden Sie das Tool Normalisierungsregel erstellen, um Werte für die Anfangsziffern, die Länge, die zu entfernenden Ziffern und die hinzuzufügenden Ziffern anzugeben, und lassen Sie dann die Skype for Business Server-Systemsteuerung das entsprechende Übereinstimmungsmuster und die entsprechende Übersetzungsregel generieren.
- [Schreiben Sie reguläre Ausdrücke manuell,](#create-or-modify-a-normalization-rule-manually) um das übereinstimmende Muster und die Übersetzungsregel zu definieren. 

## <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule"></a>Erstellen oder Ändern einer Normalisierungsregel mithilfe einer Normalisierungsregel erstellen

Führen Sie die folgenden Schritte aus, wenn Sie eine Normalisierungsregel in der Skype for Business Server-Systemsteuerung erstellen oder ändern möchten. 

**So definieren Sie eine Regel mithilfe einer Normalisierungsregel erstellen**

1. Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" am Computer an. Weitere Informationen finden Sie unter [Delegieren von Setupberechtigungen](/previous-versions/office/lync-server-2013/lync-server-2013-delegate-setup-permissions).
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Systemsteuerung zu öffnen. Weitere Informationen zu den verschiedenen Methoden zum Starten der Skype for Business-Systemsteuerung finden Sie unter [Installieren und Öffnen von Verwaltungstools](../../management-tools/install-and-open-administrative-tools.md).
3. (Optional) Führen Sie die Schritte unter [Erstellen eines Wählplans](../../deploy/deploy-enterprise-voice/dial-plans.md#to-create-a-dial-plan) durch Schritt 11 oder Ändern eines Wählplans durch Schritt 10 aus. [](../../deploy/deploy-enterprise-voice/dial-plans.md#to-modify-a-dial-plan) 
4. Geben **Sie in Neue Normalisierungsregel** oder **Normalisierungsregel** bearbeiten einen Namen ein, der das normalisierte Nummernmuster in **Name** beschreibt (z. B. **5DigitExtension**).
5. (Optional) Geben **Sie in Beschreibung** eine Beschreibung der Normalisierungsregel ein (z. B. "Übersetzt 5-stellige Erweiterungen").
6. Geben **Sie in Build a Normalization Rule** Werte in die folgenden Felder ein:
    - **Anfangsziffern**: (Optional) Geben Sie die führenden Ziffern von gewählten Nummern an, die mit dem Muster übereinstimmen soll. Geben Sie beispielsweise **425 ein,** wenn das Muster mit gewählten Nummern ab 425 übereinstimmen soll.
    - **Length**: Geben Sie die Anzahl der Ziffern im übereinstimmenden Muster an, und wählen Sie aus, ob das Muster genau mit dieser Länge übereinstimmen soll, ob gewählte Nummern mit mindestens dieser Länge übereinstimmen oder gewählten Nummern beliebiger Länge entsprechen sollen.
    - **Zu entfernende** Ziffern: (Optional) Geben Sie die Anzahl der Anfangsziffern an, die aus gewählten Nummern entfernt werden sollen, die mit dem Muster übereinstimmen sollen.
    - **Hinzuzufügende** Ziffern: (Optional) Geben Sie Ziffern an, die gewählten Nummern hinzugefügt werden sollen, die mit dem Muster übereinstimmen sollen.
    
    Die Werte, die Sie in diese Felder eingeben, werden in **Muster für Übereinstimmung** und **Übersetzungsregel angezeigt.** Wenn Sie z.  B. Startziffern leer lassen, geben Sie **7** in das Feld **Länge** die Option **Genau** aus, und geben Sie **0** in **Zu** entfernende Ziffern an. Der resultierende reguläre Ausdruck im Zu vervollständigenden Muster **ist:**

    **^(\d {7} )$**

7. Geben **Sie in** Übersetzungsregel ein Muster für das Format der übersetzten E.164-Telefonnummern wie folgt an:
    - Ein Wert, der die Anzahl der Im Vergleichsmuster angegebenen Ziffern darstellt. Wenn das Übereinstimmende Muster beispielsweise **^(\d {7} )$** ist, stellt $1 in der Übersetzungsregel 7-stellige gewählte Nummern dar.
    - (Optional) Geben Sie einen Wert in das Feld Ziffern **ein,** um das Feld hinzuzufügen, um Ziffern anzugeben, die der übersetzten Zahl voranstellen sollen (z. B. **+1425**).
    
    Wenn muster  für übereinstimmung beispielsweise **^(\d {7} )$** als Muster  für gewählte Nummern und Übersetzungsregel **+1425 $1** als Muster für E.164-Telefonnummern enthält, normalisiert die Regel 5550100 bis +14255550100.

8. (Optional) Wenn die Normalisierungsregel zu einer telefonnummer führt, die in Ihrer Organisation intern ist, wählen Sie **Interne Durchwahl aus.**
9. (Optional) Geben Sie eine Zahl ein, um die Normalisierungsregel zu testen, und klicken Sie dann auf **Los**. Die Testergebnisse werden unterhalb von **Geben Sie eine Testnummer ein** angezeigt.
    > [!Note] 
    > Sie können eine Normalisierungsregel speichern, die den Test noch nicht bestanden hat, und sie später erneut konfigurieren. Weitere Informationen finden Sie unter [Test voice routing](/previous-versions/office/lync-server-2013/lync-server-2013-test-voice-routing). 

10. Klicken Sie **auf OK,** um die Normalisierungsregel zu speichern.
11. Klicken Sie **auf OK,** um den Wählplan zu speichern.
12. Klicken Sie auf der Seite **Wähleinstellungen** auf **Commit** und anschließend auf **Commit für alle**. 
    > [!Note]
    > Wenn Sie eine Normalisierungsregel erstellen oder ändern, müssen Sie den Befehl Commit für alle ausführen, um die Konfigurationsänderung zu veröffentlichen. Weitere Informationen finden Sie [unter Publish pending changes to the voice routing configuration](/previous-versions/office/lync-server-2013/lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration). 

## <a name="create-or-modify-a-normalization-rule-manually"></a>Manuelles Erstellen oder Ändern einer Normalisierungsregel

Führen Sie die folgenden Schritte aus, wenn Sie eine Normalisierungsregel manuell erstellen oder ändern möchten.

**So definieren Sie eine Normalisierungsregel manuell**

1. Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" am Computer an. Weitere Informationen finden Sie unter [Delegieren von Setupberechtigungen](/previous-versions/office/lync-server-2013/lync-server-2013-delegate-setup-permissions).
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Systemsteuerung zu öffnen. Weitere Informationen zu den verschiedenen Methoden zum Starten der Skype for Business-Systemsteuerung finden Sie unter [Installieren und Öffnen von Verwaltungstools](../../management-tools/install-and-open-administrative-tools.md).
3. (Optional) Führen Sie die Schritte unter [Erstellen eines Wählplans](GET LINK AFTER MIGRATION) durch Schritt 11 oder Ändern eines Wählplans durch Schritt 10 aus. [](GET LINK AFTER MIGRATION)  
4. Geben **Sie in Neue Normalisierungsregel** oder **Normalisierungsregel** bearbeiten einen Namen ein, der das normalisierte Nummernmuster in **Name** beschreibt (nennen Sie beispielsweise die Normalisierungsregel **5DigitExtension**).
5. (Optional) Geben **Sie in Beschreibung** eine Beschreibung der Normalisierungsregel ein (z. B. "Übersetzt 5-stellige Erweiterungen").
6. Klicken **Sie in Build a Normalization Rule** auf **Bearbeiten**.
7. Geben Sie in Regulären Ausdruck eingeben Folgendes ein:
    - Geben **Sie unter Dieses Muster übereinstimmen** das Muster an, das Sie verwenden möchten, um der gewählten Telefonnummer zu entsprechen.
    - Geben **Sie in** Übersetzungsregel ein Muster für das Format der übersetzten E.164-Telefonnummern an.

    Wenn Sie beispielsweise **^(\d {7} )$** **in** Übereinstimmung mit diesem Muster und **+1425$1** **in** Übersetzungsregel eingeben, normalisiert die Regel 5550100 bis +14255550100.

8. (Optional) Wenn die Normalisierungsregel zu einer telefonnummer führt, die in Ihrer Organisation intern ist, wählen Sie **Interne Durchwahl aus.**
9. (Optional) Geben Sie eine Zahl ein, um die Normalisierungsregel zu testen, und klicken Sie dann auf **Los**. Die Testergebnisse werden unterhalb von **Geben Sie eine Testnummer ein** angezeigt.

    > [!Note]
    > Sie können eine Normalisierungsregel speichern, die den Test noch nicht bestanden hat, und sie später erneut konfigurieren. Weitere Informationen finden Sie unter [Test voice routing](/previous-versions/office/lync-server-2013/lync-server-2013-test-voice-routing). 

10. Klicken Sie **auf OK,** um die Normalisierungsregel zu speichern.
11. Klicken Sie **auf OK,** um den Wählplan zu speichern.
12. Klicken Sie **auf der Seite Wählplan** auf **Komma** t, und klicken Sie dann **auf Commit für alle**.