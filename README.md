# Transformacion3D


package EscalonamientoC;

import com.sun.j3d.utils.geometry.ColorCube;
import com.sun.j3d.utils.universe.SimpleUniverse;
import java.awt.BorderLayout;
import java.awt.GraphicsConfiguration;
import javax.media.j3d.Alpha;
import javax.media.j3d.BoundingSphere;
import javax.media.j3d.BranchGroup;
import javax.media.j3d.Canvas3D;
import javax.media.j3d.RotationInterpolator;
import javax.media.j3d.Transform3D;
import javax.media.j3d.TransformGroup;
import javax.swing.JFrame;
import javax.swing.JPanel;
import javax.vecmath.Vector3f;

public class EscalonamientoC extends JPanel{

     public EscalonamientoC(){
        GraphicsConfiguration config = SimpleUniverse.getPreferredConfiguration();
        Canvas3D canvas3D = new Canvas3D(config);
        
        setLayout(new BorderLayout());
        add(canvas3D);
        
        SimpleUniverse universo = new SimpleUniverse(canvas3D);
        //universo.getViewingPlatform().setNominalViewingTransform();
        //en esta parte es donde se puede modificar la vista escalonada del cubo y tambien trasladarlo a lo largo del plano
        Vector3f posicionVista = new Vector3f();
        posicionVista.z =5f;
        posicionVista.y =0f;
        posicionVista.x =0f;
        
        //traslación
        Transform3D transformVista = new Transform3D();
        transformVista.setTranslation(posicionVista);
        
        //rotación
        Transform3D rotacion = new Transform3D();
        rotacion.rotX(Math.toRadians(-45));
        rotacion.mul(transformVista);
        
        universo.getViewingPlatform().getViewPlatformTransform().setTransform(rotacion);
        universo.getViewingPlatform().getViewPlatformTransform().getTransform(transformVista);
        
        BranchGroup escena = crearGrafoEscena();
        escena.compile();
        
        universo.addBranchGraph(escena);
    }
    public BranchGroup crearGrafoEscena(){
        BranchGroup objetoRaiz = new BranchGroup();
        
        TransformGroup objetoGiro = new TransformGroup();
        objetoGiro.setCapability(TransformGroup.ALLOW_TRANSFORM_WRITE);
        objetoRaiz.addChild(objetoGiro);
        
        
        ColorCube cubo = new ColorCube(0.2f);
        objetoGiro.addChild(cubo);
        
        Alpha rotacionAlpha = new Alpha(-1,4000);
        RotationInterpolator rotacion = new RotationInterpolator(rotacionAlpha,objetoGiro);
        rotacion.setSchedulingBounds(new BoundingSphere());
        
        objetoRaiz.addChild(rotacion);
        
        return objetoRaiz;
    }
    public static void main(String[] args){
        System.setProperty("sun.awt.noerasebackground", "true");
        JFrame ventana = new JFrame("TransformGroup Java3D");
        EscalonamientoC panel = new EscalonamientoC();
        ventana.add(panel);
        ventana.setSize(700,700);
        ventana.setVisible(true);
        ventana.setLocationRelativeTo(null);
        ventana.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
    }
    
}
