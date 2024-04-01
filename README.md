1、tileLayer地址修改
  <!-- tileLayer("http://10.33.136.4:8000/data/layer/china/{z}/{x}/{y}.jpg").addTo(map$1); -->
  tileLayer("http://webrd0{s}.is.autonavi.com/appmaptile?lang=zh_cn&size=1&scale=1&style=8&x={x}&y={y}&z={z}",{ subdomains: "1234" }).addTo(map$1);
  this.map = map$1;
  this.viewer.camera.percentageChanged = 0.01;
  this.viewer.camera.changed.addEventListener(this.sceneRenderHandler, this);
  this.sceneRenderHandler();
2、TilesetLayer增加着色器
  if (this.opt.center) this.setCenter(this.opt.center);
  if (this.opt.orientation) this.setOrientation(this.opt.orientation);
  if (this.opt.scale) this.setScale(this.opt.scale);
  if (this.opt.flyTo) this.zoomTo();
  if (this.opt.style) this.updateStyle(this.opt.style);
  if (this.opt.customShader) this.setCustomShader(this.opt.customShader);

  {
      key: "setCustomShader",
      value: function setCustomShader(customShader) {
        if (!customShader) return;
        this._layer.customShader = new Cesium.CustomShader(customShader);
      }
    }