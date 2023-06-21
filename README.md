# onfido-style-issue

```ts
    export const onfidoStyle = {
      //1 rem is 16 px
      fontFamilyTitle: `"FOR smart Sans CC", helvetica, arial, sans-serif`,
      fontSizeTitle: `1.875rem`,
      fontWeightTitle: 700,
      fontFamilySubtitle: `"FOR smart Sans CC", helvetica, arial, sans-serif`,
      fontSizeSubtitle: `1rem`,
      fontWeightSubtitle: 700,
      fontFamilyBody: `"FOR smart Sans CC", helvetica, arial, sans-serif`,
      //---buttons---
      borderRadiusButton: `5px`,
      colorBackgroundButtonPrimary: `#141413`,
      colorBorderButtonPrimary: `#141413`,
      colorBackgroundButtonPrimaryHover: `#212221`,
      colorBorderButtonPrimaryHover: `#212221`,
      colorBackgroundButtonPrimaryActive: `#3b3d3e`,
      colorBorderButtonPrimaryActive: `#3b3d3e`,
      colorContentButtonSecondaryText: `#141413`,
      colorBorderButtonSecondary: `#141413`,
      colorBorderButtonSecondaryHover: `#212221`,
      colorBorderButtonSecondaryActive: `#3b3d3e`,
      colorBorderDocTypeButton: `#212221`,
      colorBorderDocTypeButtonHover: `#212221`,
      colorBorderDocTypeButtonActive: `#212221`,
      //---links---
      colorBackgroundLinkHover: `#969da3`,
      colorBackgroundLinkActive: `#6b747b`,
      colorBorderLinkUnderline: `#141413`,
      //---icons---
      colorIcon: `#141413`,
      colorInputOutline: `#141413`,
      //---info-pill---
      colorBackgroundInfoPill: `#141413`,
    };

    const instance = OnfidoSDK.init({
      useModal: true,
      isModalOpen: true,
      token: sdkToken,
      containerId: onfidoContainerId,
      workflowRunId,
      onModalRequestClose: () => {
        instance.setOptions({isModalOpen: false});
      },
      customUI: onfidoStyle,
      onUserExit: (data: UserExitCode) => {
        // eslint-disable-next-line no-console
        console.log(data);
        setOnfidoStatus(OnfidoStatus.abandoned);
      },
      onComplete: () => {
        setOnfidoStatus(OnfidoStatus.review);
      },
      onError: (error) => {
        // eslint-disable-next-line no-console
        console.log(`onfido error `, error);
        setOnfidoStatus(OnfidoStatus.error);
      },
    });
```
