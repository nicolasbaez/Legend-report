# Legend-report
intermission

![buh](https://github.com/nicolasbaez/Legend-report/blob/main/xp028.gif)
```javascript
k = 25;
setup = (_) => createCanvas((w = 500), w, WEBGL);
draw = (_) => {
  h = w / 2;
  colorMode(HSB, k);
  clear();
  rotateX(k);
  rotateY(k / 2);
  for (i = 0; i < k; i++)
    for (j = 0; j < k; j++) {
      normalMaterial();
      push();
      translate(i * k - h, j * k - h, -h + noise(i, j) * w);
      rotateX(i * k);
      rotateY(j + k);
      box(noise(i, j) * 50);
      pop();
    }
  k += 0.01;
};

keyPressed = (_) => {
  if (key === "s") {
    saveGif("xp028.gif", 350, { delay: 0, units: "frames" });
  }
};
