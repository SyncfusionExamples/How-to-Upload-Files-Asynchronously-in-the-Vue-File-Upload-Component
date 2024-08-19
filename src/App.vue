<template>
  <div class="container">
    <ejs-uploader
    :asyncSettings="asyncSettings"
    :sequentialUpload="true"
    :autoUpload="false"
    :directoryUpload="true"
    >
<!--     <e-files>
      <e-uploadedfiles name="Nature" size="11000" type=".png"></e-uploadedfiles>
    </e-files> -->
  </ejs-uploader>
  </div>
</template>

<script>

import { UploaderComponent, FilesDirective, UploadedFilesDirective } from "@syncfusion/ej2-vue-inputs";

export default {
  components: {
    "ejs-uploader": UploaderComponent,
    "e-files": FilesDirective,
    "e-uploadedfiles": UploadedFilesDirective
  },
  data: function () {
    return {
      asyncSettings: {
        saveUrl: 'https://services.syncfusion.com/vue/production/api/FileUploader/Save',
        removeUrl: 'https://services.syncfusion.com/vue/production/api/FileUploader/Remove',
        chunkSize:50000,
        retryAfterDelay: 1000,
        retryCount: 2
      }
    }
  }
}
</script>

<style>
@import "../node_modules/@syncfusion/ej2-base/styles/material.css";
@import "../node_modules/@syncfusion/ej2-buttons/styles/material.css";
@import "../node_modules/@syncfusion/ej2-vue-inputs/styles/material.css";

.container {
  position: absolute;
  top: 15%;
  left: 40%;
  width: 250px;
}
</style>