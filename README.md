1、tileLayer地址修改
  <!-- tileLayer(this.opt.url).addTo(map$1); -->
  tileLayer(this.opt.url,this.opt.layer).addTo(map$1);
  this.map = map$1;
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

3.if (!that.canRemove) return;that被写成了this
  this.handler.setInputAction(function (evt) {
  if (!that.canRemove) return;
  /* console.log("that===>",that);*/

  if (!that.canEdit) return; // 若当前正在绘制 则无法进行删除

4、图上量算 三角测量 空间距离 水平距离重叠

    <!-- var space_mid = Cesium.Cartesian3.midpoint(that.endPosition, that.firstPosition, new Cesium.Cartesian3()); -->
    var space_mid = Cesium.Cartesian3.midpoint(that.endPosition, that.endPosition, new Cesium.Cartesian3());
    that.spaceDistancefloatLabel.show = true;
    that.spaceDistancefloatLabel.position.setValue(space_mid);
    var text3 = that.formateLength(spaceDistance, that.unit);
    that.spaceDistancefloatLabel.label.text = "空间距离：" + text3;
    that.spaceDistancefloatLabel.length = spaceDistance;