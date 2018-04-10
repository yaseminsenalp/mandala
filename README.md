# mandala
int anglestep = 15;

void setup () {
  size(800, 800);
  background(0);

  drawTemplate();
}
void drawTemplate() {
  stroke(255, 100);
  pushMatrix();
  translate(width*0.5, height*0.5);

  for (int i = 0; i < 360; i += anglestep) {
    rotate(radians(anglestep));
    line(0, 0, width, 0);
  }
  popMatrix();
}

void draw () {

  if (mousePressed) {
    pushMatrix();
    translate(width*0.5, height*0.5);

    for (int i = 0; i < 360; i += anglestep) {
      rotate(radians(anglestep));
      stroke(0, 125, 0, 255);
      fill(#D894E8);
      ellipse(pmouseX-width*0.5, pmouseY-height*0.5, mouseX-width*0.5, mouseY-height*0.5);
      line(-(pmouseX-width*0.5), pmouseY-height*0.5, -(mouseX-width*0.5), mouseY-height*0.5);
    }
    popMatrix();
  }
}
void keyPressed(){
if(key == 's' || key == 'S')
background(0);
drawTemplate();
}
