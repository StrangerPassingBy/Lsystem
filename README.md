# Lsystem
int SZ = 800;  // screen size
Tree tree;
  
void settings() {
  // In newer versions of Processing, if we want to
  // set the screen size using variables (such as SZ here)
  // we need to do so within the settings() function, not
  // within the normal setup() function.
  // See https://processing.org/reference/settings_.html
  size(SZ,SZ);  
}

void setup() {
  int d = 100;
  int x = SZ/2;
  int y = SZ/2;
  float branchAngle = radians(180);
  float branchAngle_Left = radians(-45); 
  float branchAngle_Right = radians(45); 
  float initOrientation = PI;  
  String state = "F";           //f[+F&F&F&F
  float  scaleFactor = 0.8;      
  String F_rule = "F[+sH]s+F";  //FH+ // Fs[+&-F]  //s[+H]&fF      
  String H_rule = "";  //HF- //H[-sF] [&fsF] //F[t-sH]s+F
  String f_rule = "";           
  int numIterations = 6;
  
  background(255);
  noLoop();
  
  tree = new Tree(d, x, y, branchAngle, branchAngle_Right, branchAngle_Left, initOrientation, state, scaleFactor, F_rule, H_rule, f_rule, numIterations);  
}

void draw() {
  tree.draw();
 
}
