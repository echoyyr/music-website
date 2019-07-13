<template>
    <div>
        <div id="container"></div>
    </div>
</template>


<script>
    import * as Three from 'three'
    import OrbitControls from 'three-orbitcontrols'
    import {OBJLoader} from 'three-obj-mtl-loader'
    // import OBJLoader from 'three-obj-loader'
    import Stats from 'stats-js'


    export default {
        name: 'ThreeTest',
        data() {
            return {
                camera: null,
                scene: null,
                renderer: null,
                mesh: null,
                controls:null
            }
        },
        methods: {
            init() {
                let container = document.getElementById('container');

                this.camera = new Three.PerspectiveCamera(70, container.clientWidth/container.clientHeight, 0.01, 1000);
                this.camera.position.z = -86;


                this.scene = new Three.Scene();
                new  OBJLoader().load('/tea.obj', obj=> {
                    let materialObj = new Three.MeshBasicMaterial({
                        vertexColors: Three.FaceColors,
                    });
                    obj.traverse(function(child) {
                        if (child instanceof Three.Mesh) {
                            child.material = materialObj;
                        }
                    });
                    this.scene.add(obj);
                });


                console.log(this.scene);


                this.renderer = new Three.WebGLRenderer({antialias: true});
                this.renderer.setSize(container.clientWidth, container.clientHeight);
                this.renderer.setClearColor(0xffffff);

                this.OrbitControls=new Three.OrbitControls(this.camera, this.renderer.domElement);

                container.appendChild(this.renderer.domElement);

            },
            animate() {
                if(this.obj){
                    this.obj.rotation.x += 0.01;
                    this.obj.rotation.y += 0.02;
                }
                requestAnimationFrame(this.animate);
                this.renderer.render(this.scene, this.camera);

            }
        },
        mounted() {
            this.init();
            this.animate()
        }
    }
</script>
<style scoped>
    #container {
        height: 500px;
        width: 500px;
    }

</style>













